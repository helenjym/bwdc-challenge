<script>
    import * as Highcharts from "highcharts";
    import "highcharts/modules/exporting";
    import { Chart } from "@highcharts/svelte";
    import Scroller from "../lib/Scroller.svelte";
    import ArticleText from "../lib/ArticleText.svelte";

</script>



<div class='wrapper'>
            <div class="maps">
                <div class='map'>
                    <p class='subtitle'>Bachelor degree attainment (Black)</p>
                    <img class='map black' src='bachelor_degree_attainment_black_transparent.png' alt='Map of bachelor degree attainment (Black)'>
                </div>
                <div class='map'>
                    <p class='subtitle'>Bachelor degree attainment (White)</p>
                    <img class='map white' src='bachelor_degree_attainment_white_transparent.png' alt='Map of bachelor degree attainment (White)'>
                </div>
            </div>
    <img class='scale' src='bachelor_degree_scale.png' alt='bachelor degree attainment scale'>

</div>



<style>
    .wrapper {
        background-color: #f7f5eb;
        /* border-style: solid;
        border-color: #4096fa; */
        display: flex;
        flex-direction: column; 
         align-items: center; 
        justify-content: center; 
         /* padding: min(100vh, 30rem) 1rem;  */

    }

    .map {
        background-color: #f7f5eb;
        width: 50vh;
        height: 50vh;
    }
    .maps {
        background-color: #f7f5eb;
        display: flex;
        flex-wrap: wrap; 
        align-items: center;
        justify-content: center;
    }
    .map {
        display: flex;
        flex-direction: column;
        align-items: center;
    }
    .subtitle {
        color: #702d00;
        padding: 10px;
        border-style: solid;
        border-radius: 10px;
    }

    .scale {
        width: 50vh;
        margin-top: 110px;

    }
</style>