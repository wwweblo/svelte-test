<script>
    import {createEventDispatcher} from 'svelte';
    export let user = {id:undefined, name:undefined};

    const dispatch =  createEventDispatcher();

    function handleDelete(id){
        dispatch('delete-user',id)
    };
</script>

<div class="userCard">
    {user.name}
    <button
        class="ghost-button"
        on:click={() => handleDelete(user.id)}
    >
        x
    </button>
</div>

<style>
    .userCard{
        background-color: white;
        border-radius: 5px;
        padding: 0.5rem 1rem;
        width: 100%;
        flex-shrink: 0;
        display: flex;
        justify-content: space-between;
    }
    .userCard:hover{
        box-shadow: 2px 2px 6px lightgrey;
    }

    .ghost-button{
        cursor: pointer;
        background: transparent;
        border: none;
        transition: all 0.3s;
        border-radius: 50%;
        padding: 2px;
    }
    .ghost-button:active{
        background-color: lightgray;
    }
</style>