<script>
    export let usersCount;
    export let averageAge;
</script>

<section>
    <div class="card">
        <div>users:{usersCount}</div>
        <div>average age:{averageAge.toFixed(2)}</div>
    </div>
</section>

<style>
    .card{
        background-color: #fff;
        border-radius: 10px;
        padding: 0.5rem 1rem;
        box-shadow: 2px 2px 6px lightgray;
    }
</style>