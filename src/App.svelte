<script>
	import { each } from "svelte/internal";
  
	  let showUsers = false;
	  let users = [
		  {id: 1, name: "Bob"},
		  {id: 2, name: "Alice"},
		  {id: 3, name: "Ben"},
	  ];
  
	  function addUser (name) {
		  if (name) {
			  const newUser  = {
				  id: users.length + 1,
				  name: name
			  };
			  users = [...users, newUser ];
		  }
	  }
  
	  function toggleBool() {
		  showUsers = !showUsers;
	  }
  </script>
  
  <main>
	  <section>
		  <input
			  type="text"
			  id="userInput"
			  placeholder="Enter the name..." >
		  <button on:click={() => addUser (document.getElementById('userInput').value)}>
			  submit
		  </button>
	  </section>
	  <section class="horisontalFlex">
		  <input
			  type="checkbox"
			  name="showUsersBox" 
			  id="showUsersBox"
			  on:change={toggleBool}
		  >
		  <label for="showUsersBox">Show Names</label>
	  </section>
	  {#if showUsers}
		  <ol>
			  {#each users as user (user.id)}
				  <li>
					  {user.name}
				  </li>
			  {/each}
		  </ol>
	  {/if}
  </main>
  
  <style>
	  .horisontalFlex {
		  display: flex;
		  flex-direction: row;
		  gap: 1rem;
	  }
  </style>