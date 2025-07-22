<script>
	import ArticleText from "../lib/ArticleText.svelte";
    import Scroller from "../lib/Scroller.svelte";


</script>


<div>
    <Scroller layout="right">
        {#snippet sticky()}
            <img class='background' src='loc-mow.jpg' alt="Protestors at the 1963 March on Washington hold up various signs demanding freedom and equality">
            <p>Civil rights March on Washington, D.C. August 28, 1963 <a href=https://www.loc.gov/item/2003654393>(Library of Congress)</a></p>
        {/snippet}
        {#snippet scrolly()}
            <ArticleText>
                <p>Over 60 years since the March on Washington for Jobs and Freedom, the struggle for racial equality in America continues⁠—including in the nation’s capital. </p>
            </ArticleText>
             <!-- <ArticleText>
                <p>D.C. has a higher proportion of Black residents than any state in the U.S., but racial inequities rooted in systemic racial discrimination uphold significant barriers to wealth accumulation for many Black households in the district. </p>
            </ArticleText> -->
        {/snippet}
    </Scroller>
</div>


<style>
    .background {
        width: 100vh;
        height: 60vh;
        object-fit: cover;
        margin-left: 30px;
        border-style: solid;
        border-color: #702d00;

    }
    p {
        font-size: small;
        color: #702d00;
    }
</style>