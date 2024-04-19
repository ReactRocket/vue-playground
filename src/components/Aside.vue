<template>
    <div v-for="data in dataList">
        <h3>{{ data.category }}
            <button @click="activeList.push(data.category)">+</button></h3>
        <ul v-if="activeList.includes(data.category)">
            <li v-for="item in data.items">{{ item }}</li>
        </ul>
    </div>
</template>

<script>
export default {
    name: "SideBar",
    props: ['dataList'],
    data() {
        return {
            activeList: []
        }
    }
}
</script>

<style scoped></style>