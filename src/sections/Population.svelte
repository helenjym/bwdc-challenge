<script>
    import * as Highcharts from "highcharts";
    import "highcharts/modules/exporting";
    import { Chart } from "@highcharts/svelte";
    import Scroller from "../lib/Scroller.svelte";
    import ArticleText from "../lib/ArticleText.svelte";

    let options = {
        chart: {
            type: "pie",
        },
        title: {
            text: "Population Distribution in D.C.",
        },
        plotOptions: {
            pie: {
                allowPointSelect: true,
                dataLabels: [
                    {
                        enabled: true,
                        distance: 20,
                    },
                    {
                        enabled: true,
                        distance: -40,
                        format: "{point.percentage:.1f}%",
                        style: {
                            fontSize: "1.2em",
                            textOutline: "none",
                        },
                        filter: {
                            operator: ">",
                            property: "percentage",
                            value: 10,
                        },
                    },
                ],
            },
        },
        series: [
            {
                name: "Group",
                data: [
                    {
                        name: "Black",
                        y: 151,
                    },
                    {
                        name: "White",
                        y: 180,
                    },
                    {
                        name: "Hispanic",
                        y: 32,
                    },
                    {
                        name: "Asian",
                        y: 103,
                    },
                    {
                        name: "Other",
                        y: 77,
                    },
                ],
            },
        ],
    };
</script>


<style>
    .chart {
        width: 90%;
        margin: 0px auto;
    }
</style>