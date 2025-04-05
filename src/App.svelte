<script>

  import UserList from "./components/UserList.svelte";
  import UserForm from "./components/UserForm.svelte";

  let users = [
    {id: 1, name: 'John'},
    {id: 2, name: 'Ben'},
    {id: 3, name: 'Bob'},
    {id: 4, name: 'Alice'},
    {id: 5, name: 'Alan'},
    {id: 6, name: 'Bruce'},
  ]

  function deleteUser(e){
    const id = e.detail;
    users = users.filter((item)=> item.id != id)
  }
  function addUser(e){
    const name = e.detail;
    const id = users.length+1;

    users = [...users, {id, name}]

    console.log(users)
  }
</script>

<main>
  <UserForm on:add-user={addUser}/>
  <UserList
    {users}
    on:delete-user={deleteUser}/>
</main>

<style>
  main{
    display: flex;
    flex-direction: column;
    align-items: center;
    gap:1rem;
  }
</style>