<script>
    import * as Highcharts from "highcharts";
    import "highcharts/modules/exporting";
    import { Chart } from "@highcharts/svelte";
    import Scroller from "../lib/Scroller.svelte";
    import ArticleText from "../lib/ArticleText.svelte";
    import { onMount } from "svelte";
	import ObservedArticleText from "../lib/ObservedArticleText.svelte";

    let options = {
        chart: {
            type: 'column',
            backgroundColor: 'transparent'

        },
        title: {
            text: 'Education attainment in D.C. (2023)'
            
        },
        subtitle: {
            text: 'Source: Black Wealth Data Center'
        },
        xAxis: {
            categories: ['High school diploma', 'Bachelors degree or higher']
        },
        yAxis: {
            min: 0,
            max: 100,
            title: {
                text: 'Percentage attainment'
            }
        },
        plotOptions: {
            column: {
                pointPadding: 0.2,
                borderWidth: 0
            }
        },
        series: [
            {
                name: 'Black',
                data: [88.5, 33.3]
            },
            {
                name: 'White',
                data: [99.1, 92]
            }
        ],
        colors: ['#5d0070', '#000d70']
    }
    
    let visible = $state(false)

    let optionsTwo = {
        threshold: [0.85, 0.95],
    }

    const callback = (entries, observer) => {
        entries.forEach((entry) => {
            const elem = entry.target;
            if (entry.intersectionRatio >= 0.9) {
                visible=false;
                
            } else if (entry.intersectionRatio < 0.9) {
                visible=true;
            }
        });
    }
</script>



<div>
    <Scroller layout="left">
        {#snippet scrolly()}
                 <ObservedArticleText {callback} options={optionsTwo}>Education attainment is strongly linked to higher income and D.C. has some of the highest rates of education attainment across the country. However, disparities are stark as education attainment rates is significantly lower for Black population in D.C., which may indicate a lack of adequate support in predominantly Black schools. </ObservedArticleText>

            <!-- <div class="maps">
                <div class='map'>
                    <p class='subtitle'>Bachelor degree attainment (Black)</p>
                    <img class='map black' src='bachelor_degree_attainment_black_transparent.png' alt='Map of bachelor degree attainment (Black)'>
                </div>
                <div class='map'>
                    <p class='subtitle'>Bachelor degree attainment (White)</p>
                    <img class='map white' src='bachelor_degree_attainment_white_transparent.png' alt='Map of bachelor degree attainment (White)'>
                </div>
                            <img class='scale' src='bachelor_degree_scale.png' alt='bachelor degree attainment scale'>

            </div> -->
            <!-- <div class="space">
            </div>  -->
        {/snippet}
        {#snippet sticky()}
                    <div class="chart">
                <Chart {options} highcharts={Highcharts}></Chart>
            </div>

        {/snippet}
    </Scroller>
</div>


<style>
    /* .chart {
        margin: 50vh auto;
        margin-bottom: 30vh;
        width: 60%;
        padding: 20px;
    } */

    /* .space {
        margin: 30vh;
    } */
    .wrapper {
        background-color: #f7f5eb;
        /* border-style: solid;
        border-color: #4096fa; */
         display: flex;
        flex-direction: row;
        align-items: center; 

    }

    .map {
        background-color: #f7f5eb;
        width: 50vh;
        height: 50vh;
    }
    .maps {
        background-color: #f7f5eb;
        display: flex;
        padding: 50vh auto;
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
        width: 40vh;
        align-self: flex-end;
    }
</style>