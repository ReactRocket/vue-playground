<template>
    <div class="output" v-html="codeValue"></div>
</template>

<script>
export default {
    name: "Preview",
    props: ['codeValue']

}
</script>

<style scoped>
.output {
    color: black;
    border: none;
    border-right: 1px solid #ccc;
    resize: none;
    outline: none;
    background-color: #f6f6f6;
    font-size: 14px;
    font-family: 'Monaco', courier, monospace;
    padding: 20px;
    overflow: auto;
    width: 100%;
    height: 100%;
    box-sizing: border-box;
    padding: 0 20px;
    border-radius: 0 10px 10px 0;

}
</style>