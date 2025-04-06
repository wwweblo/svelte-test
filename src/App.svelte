<script>

  import UserList from "./components/UserList.svelte";
  import UserForm from "./components/UserForm.svelte";
  import UsersStats from "./components/UsersStats.svelte";

  let users = [
    {id: 1, name: 'John', age: 16},
    {id: 2, name: 'Ben', age: 24},
    {id: 3, name: 'Bob', age: 54},
    {id: 4, name: 'Alice', age: 47},
    {id: 5, name: 'Alan', age: 19},
    {id: 6, name: 'Bruce', age: 35},
  ]

  function deleteUser(e){
    const id = e.detail;
    users = users.filter((item)=> item.id != id)
  }
  function addUser(e){
    const {name, age} = e.detail;
    const id = users.length+1;

    users = [...users, {id, name, age}]
  }

  $: count = users.length;
  $: averageAge = users.reduce((accumulator, user) =>
        accumulator + user.age, 0) / count
</script>

<main>
  <UserForm on:add-user={addUser}/>
    {#if count > 0}
    <UsersStats
      averageAge={averageAge}
      usersCount={count}
    />
    
    <UserList
      {users}
      on:delete-user={deleteUser}/>

    {:else}
      <h1>No users 😭</h1>
    {/if}
</main>

<style>
  main{
    display: flex;
    flex-direction: column;
    align-items: center;
    gap:1rem;
  }
</style>