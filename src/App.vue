<script>
    import opand from "./components/library/verilog/operators/opand"
    import opor from "./components/library/verilog/operators/opor"
    import opnor from "./components/library/verilog/operators/opnor"
    import opnand from "./components/library/verilog/operators/opnand"
    import opxor from "./components/library/verilog/operators/opxor"
    import opnot from "./components/library/verilog/operators/opnot"

    export default {
        name: "App",
        components: {
            opand,
            opor,
            opnor,
            opnand,
            opxor,
            opnot
        }
    }
</script>

<style>
    .app {
        display: flex;
        flex-direction: column;
        align-items: flex-start;
    }
    .topic {
        margin-bottom: 10px;
    }
    .topic > .content {
        padding: 3px 3px 3px 8px;
        font-family: Verdana, Geneva, Tahoma, sans-serif;
        font-size: 12px;
    }
</style>

<template>
    <div class="app">
        <opand></opand>
        <opor></opor>
        <opnot></opnot>
        <opnor></opnor>
        <opnand></opnand>
        <opxor></opxor>
    </div>
</template>
