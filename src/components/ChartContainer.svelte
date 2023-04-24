<script>
    import LineChart from "./LineChart.svelte";

    export let type;
    export let chartProps;

    const chartTypes = {
        linechart: LineChart,
    };
</script>

<section class="container">
   <!--  <h2>Hello World</h2> -->
    <svelte:component this={chartTypes[type]} {...chartProps} />
</section>


<style>
    .container {
        max-width: 640px;
        border: solid 1px black;
        margin: auto;
    }
</style>