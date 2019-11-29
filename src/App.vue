<script>
    import opand from "./components/library/verilog/operators/opand"

    export default {
        name: "App",
        components: {
            opand
        }
    }
</script>

<style>
    .app {
        display: flex;
        flex-direction: column;
        align-items: flex-start;
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
    </div>
</template>
