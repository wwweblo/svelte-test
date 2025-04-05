<script>
    import { createEventDispatcher } from 'svelte';
    const dispatch = createEventDispatcher();

    function addUser (name) {
        dispatch('add-user', name);
    }
</script>

<section>
    <input type="text" id="userInput" placeholder="Enter a name...">
    <button on:click={() => {
        const inputElement = document.getElementById('userInput');
        addUser (inputElement.value);
        inputElement.value = '';
    }}>Submit</button>
</section>