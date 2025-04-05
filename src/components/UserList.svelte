<script>
    import UserItem from "./UserItem.svelte";

    export let users = [];
</script>

<section class="usersList">
    {#each users as user (user.id)}
        <UserItem {user} on:delete-user/>
    {/each}
</section>

<style>
    .usersList{
        display: flex;
        flex-direction: column;
        gap: 0.5rem;
        flex-shrink: 0;
        min-width: 300px;
    }
</style>