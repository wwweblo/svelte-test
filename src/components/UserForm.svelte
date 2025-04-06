<script lang="ts">
    import { createEventDispatcher } from 'svelte';
    const dispatch = createEventDispatcher();
    
    let name = '';
    let age = '18';

    function addUser() {
        dispatch('add-user', {name, age});
        name = '';
        age = '18';
    }
</script>

<section>
    <input type="text" bind:value={name} placeholder="Enter a name...">
    <input type='number' bind:value={age} placeholder="18">
    <button on:click={addUser}>Submit</button>
</section>