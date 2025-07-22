<script>
    let { title, subtitle, author } = $props();
</script>

<div class="title-card">
    <div class="content">
        <h1>{title}</h1>
        <p>{author}</p>
        <p>{subtitle}</p>
    </div>
</div>

<style>
    .title-card {
        background-color: #f7f5eb;

        height: 100vh;
        display: flex;
        justify-content: center;
        align-items: center;
        text-align: center;
        padding: 2rem;
        box-sizing: border-box;
        font-family: "Inter", sans-serif;
    }

    .content {
        max-width: 700px;
        background-color: #ffd7be;
        color: #702d00;
        border: solid #702d00 3px;        
        padding: 2rem;
        /* border: 6px solid #e3ff00; */
        border-radius: 2rem;
        box-shadow: 16px 16px #702d00;
    }

    h1 {
        font-size: 3rem;
        margin: 0;
        color: #702d00;
        text-shadow: 1px 1px 0 #702d00;
    }

    p {
        font-size: 1.3rem;
        color: #702d00;
        margin-top: 1rem;
    }

    @media (max-width: 600px) {
        h1 {
            font-size: 2.2rem;
        }

        p {
            font-size: 1.1rem;
        }
    }
</style>
