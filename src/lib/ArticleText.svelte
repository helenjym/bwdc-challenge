<script>
    let { children } = $props();
</script>

<div class="article-text">
    <p>
        {@render children()}
    </p>
</div>

<style>
    .article-text {
        margin: 50vh auto;
        width: 60%;
        background-color: #ffd7be;
        color: #702d00;
        border: solid #702d00 3px;
        padding: 20px;
        /* box-shadow: 16px 16px hsl(318, 100%, 79%); */
    }
</style>
