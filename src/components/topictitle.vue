<script>
    export default {
        name: "topictitle",
        props: {
            desc: {default: null}
        }
    }
</script>

<style scoped>
    .topictitle {
        min-width: 200px;
    }
    .title {
        font-family: monospace;
        font-size: 16px;
        padding: 2px;
        border-bottom: 1px solid rgba(0, 0, 0, 0.185);
    }
</style>

<template>
    <div class="topictitle">
        <div class="title">{{ desc }}</div>
    </div>
</template>
