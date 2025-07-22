<script>
        import { fade, fly } from "svelte/transition";
        import ArticleText from "../lib/ArticleText.svelte";
	import ObservedArticleText from "../lib/ObservedArticleText.svelte";
    import Scroller from "../lib/Scroller.svelte";

    let visible = $state(false)
    let showToggle = $state(false)

    const options = {
        threshold: [0.85, 0.95],
    };

    const callback = (entries, observer) => {
        entries.forEach((entry) => {
            const elem = entry.target;
            if (entry.intersectionRatio >= 0.9) {
                showToggle=true;
                
            } else if (entry.intersectionRatio < 0.9) {
                showToggle=false;
            }
        });
    };

</script>


<div>

    <Scroller layout="right">
        {#snippet sticky()}
            {#if showToggle}
                {#if !visible}
                    <div class='map'>
                        <div class='div'>
                            <img class='map ed' src='bachelor_degree_attainment_black_transparent.png' alt='Map of Black bachelor degree attainment in D.C.'/>
                            <p>Bachelor degree attainment (Black)</p>
                            <img class='scale' src='bachelor_degree_scale.png' alt='bachelor degree attainment scale'>
                            <button onclick={()=>visible=!visible} class='toggle'>Click to see broadband internet access</button>
                        </div>
                    </div>
                {:else}
                    <div class='map'>
                        <div class='div'>
                            <img class='map internet' src='broadband_access_black_transparent.png' alt='Map of broadband internet access across Black households in D.C.'/>
                            <p>Broadband internet access (Black)</p>
                            <img class='scale' src='broadband_access_scale.png' alt='broadband access attainment scale'>
                            <button onclick={()=>visible=!visible} class='toggle'>Click to see bachelor degree attainment</button>
                        </div>
                    </div>
                {/if}
            {/if}
        {/snippet}
        {#snippet scrolly()}
    <ObservedArticleText {callback} {options}>
                Broadband internet access across Black households in D.C. is 4 percentage points lower than the national average. Internet is a vital resource to education and students without it may not be able to complete coursework or supplementary lessons from home, posing a significant barrier to their progress in school.
    </ObservedArticleText>
        {/snippet}
    </Scroller>
</div>


<style>
    .ed {
        width: 50vh;
        height: 50vh;
        margin-top: 5px;
        /* object-fit: cover; */
    }
    .internet {
        height: 50vh;
        margin-right: 7px;
    }
    .scale {
        margin: 20px;
        width: 40vh;
        align-self: flex-end;
    }

    .map {
        display: flex;
        align-content: center;
        justify-content: center;

    }

    .div {
        display: flex;
        align-items: center;
        flex-direction: column;
                transform: translateY(20%);

    }

    button {
        background-color: #ffd7be;
        color: #702d00;
        font-size: 18px;
        border-style: solid #702d00;
        border-radius: 5px;
        margin-top: 10px;
    }
</style>