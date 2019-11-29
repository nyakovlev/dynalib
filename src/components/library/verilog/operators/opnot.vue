<script>
    import topictitle from "../../../topictitle"

    export default {
        name: "opnot",
        components: {
            topictitle
        },
        data() {
            return {
                env: {a: 1, b: 0},
                focus_cmb: null,
                combos: [
                    {a: 1, b: 0},
                    {a: 0, b: 1}
                ]
            }
        }
    }
</script>

<style scoped>
    .live_diagram {
        width: 200px;
        height: 100px;
        position: relative;
    }
    .wires {
        position: absolute;
        left: 0;
        top: 0;
        width: 100%;
        height: 100%;
    }
    .gate {
        width: 50px;
        height: 40px;
        position: absolute;
        left: 50%;
        top: 50%;
        transform: translate(-50%, -50%);
    }
    .input_a, .output_b {
        position: absolute;
        transform: translate(-50%, -50%);
    }
    .input_a {
        left: 39px;
        top: 50%;
    }
    .output_b {
        left: 79%;
        top: 50%;
    }
    table {
        margin: 5px 0;
        cursor: pointer;
    }
    .title_tr {
        background-color: rgb(226, 226, 226);
        font-weight: bold;
    }
    td {
        padding: 2px;
        border: 1px solid rgba(0, 0, 0, 0.253);
    }
    .bit {
        width: 16px;
        height: 16px;
        font-family: 'Courier New', Courier, monospace;
        font-size: 14px;
        font-weight: bold;
        color: white;
        background-color: grey;
        text-align: center;
        margin: 0 auto;
    }
    .bit_0 {
        background-color: rgb(0, 68, 170);
    }
    .bit_1 {
        background-color: rgb(7, 110, 7);
    }
    .value_tr {
        opacity: 0.6;
    }
    .focused {
        opacity: 1;
    }
</style>

<template>
    <div class="topic">
        <topictitle :desc="'NOT Gate'"></topictitle>
        <div class="content">
            <div class="live_diagram">
                <img class="wires" src="./wires_1_1.svg">
                <img class="gate" src="./not_gate.svg">
                <div class="input_a bit" v-bind:class="{bit_0: !env.a, bit_1: env.a}">{{ env.a }}</div>
                <div class="output_b bit" v-bind:class="{bit_0: !env.b, bit_1: env.b}">{{ env.b }}</div>
            </div>
            Inverts the data; if the input is <b>1</b>, the output is <b>0</b>, and vice versa.
            <br>
            The table below shows all possible combinations of this operator:
            <table @mouseleave="focus_cmb = null; env = {a: 1, b: 0}">
                <tr class="title_tr">
                    <td>Input A</td>
                    <td>Output B</td>
                </tr>
                <tr v-for="(c, cindex) in combos" :key="cindex"
                    @mouseover="focus_cmb = cindex; env = c"
                    class="value_tr" v-bind:class="{focused: focus_cmb == null || focus_cmb == cindex}"
                >
                    <td><div class="bit" v-bind:class="{bit_0: !c.a, bit_1: c.a}">{{ c.a }}</div></td>
                    <td><div class="bit" v-bind:class="{bit_0: !c.b, bit_1: c.b}">{{ c.b }}</div></td>
                </tr>
            </table>
            (Hover over a table row to see it in the diagram)
        </div>
    </div>
</template>
