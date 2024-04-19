<template>
    <div>
        <textarea class="input" :value="codeValue" @input="$emit('change-code', $event.target.value)"></textarea>
    </div>
</template>

<script>
export default {
    name: "Code",
    props: ['codeValue']
}
</script>

<style scoped>
.input {
    color: var(--color-1);
    border: none;
    border-right: 1px solid #ccc;
    resize: none;
    outline: none;
    background-color: var(--color-8);
    font-size: 14px;
    font-family: 'Monaco', courier, monospace;
    overflow: auto;
    width: 100%;
    height: 100%;
    box-sizing: border-box;
    padding: 20px;
    border-radius: 10px 0 0 10px;
    overflow-y: auto;
    overflow-x: hidden;
    word-wrap: break-word;
}
</style>