<template>
    <div class="chart" ref="chartdiv">
    </div>
</template>

<script>
    import * as am4core from "@amcharts/amcharts4/core";
    import * as am4charts from "@amcharts/amcharts4/charts";

    export default {
        name: "Radar",
        mounted: function () {
            let chart = am4core.create(this.$refs.chartdiv, am4charts.RadarChart);

            //chart.dataSource.url = "chart_data.json";

            chart.data = [
                {
                    "country": "Lithuania",
                    "litres": 501
                }, {
                    "country": "Czech Republic",
                    "litres": 301
                }, {
                    "country": "Ireland",
                    "litres": 266
                }, {
                    "country": "Germany",
                    "litres": 165
                }, {
                    "country": "Australia",
                    "litres": 139
                }, {
                    "country": "Austria",
                    "litres": 336
                }, {
                    "country": "UK",
                    "litres": 290
                }, {
                    "country": "Belgium",
                    "litres": 325
                }, {
                    "country": "The Netherlands",
                    "litres": 40
                }
            ];

            /* Create axes */
            let categoryAxis = chart.xAxes.push(new am4charts.CategoryAxis());
            categoryAxis.dataFields.category = "country";

            let valueAxis = chart.yAxes.push(new am4charts.ValueAxis());

            /* Create and configure series */
            let series = chart.series.push(new am4charts.RadarSeries());
            series.dataFields.valueY = "litres";
            series.dataFields.categoryX = "country";
            series.name = "Sales";
            series.strokeWidth = 3;
        }
    }
</script>

<style scoped>
    .chart {
        width: 100%;
        height: 500px;
    }
</style>