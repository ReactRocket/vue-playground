<template>
    <div>
        <Code :code-value="code" @change-code="changeCode" />
        <Preview :code-value="code" />
    </div>
</template>

<script>
import Code from '@/components/Code.vue';
import Preview from '@/components/Preview.vue';

export default {
    name: "Home",
    components: {
        Code,
        Preview
    },
    data() {
        return {
            code: `<h1 style="color:red; width:100%;" align="center">Hello World</h1>`
        }
    },
    methods: {
        changeCode(code) {
            this.code = code;
        }
    }
}
</script>

<style scoped>
div {
    height: 100%;
    width: 100%;
    display: flex;
    overflow: hidden;
}
</style>