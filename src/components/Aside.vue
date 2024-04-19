<template>
    <div id="container">
        <div v-for="data in dataList">
            <p :style="data.items.includes(activeItem) ? { color: 'white', background: 'green' } : ''" :id="'heading'">
                {{ data.category }}
                <template v-if="!activeList.includes(data.category)">
                    <svg @click="activeList.push(data.category)" xmlns="http://www.w3.org/2000/svg" width="16"
                        height="16" fill="currentColor" class="bi bi-plus-circle" viewBox="0 0 16 16">
                        <path d="M8 15A7 7 0 1 1 8 1a7 7 0 0 1 0 14m0 1A8 8 0 1 0 8 0a8 8 0 0 0 0 16" />
                        <path
                            d="M8 4a.5.5 0 0 1 .5.5v3h3a.5.5 0 0 1 0 1h-3v3a.5.5 0 0 1-1 0v-3h-3a.5.5 0 0 1 0-1h3v-3A.5.5 0 0 1 8 4" />
                    </svg>
                </template>
                <template v-else>
                    <svg @click="activeList = activeList.filter(val => val != data.category)"
                        xmlns="http://www.w3.org/2000/svg" width="16" height="16" fill="currentColor"
                        class="bi bi-dash-circle" viewBox="0 0 16 16">
                        <path d="M8 15A7 7 0 1 1 8 1a7 7 0 0 1 0 14m0 1A8 8 0 1 0 8 0a8 8 0 0 0 0 16" />
                        <path d="M4 8a.5.5 0 0 1 .5-.5h7a.5.5 0 0 1 0 1h-7A.5.5 0 0 1 4 8" />
                    </svg></template>
            </p>
            <ul v-if="activeList.includes(data.category)">
                <li v-for="item in data.items" :id="activeItem == item && 'active'" @click="activeItem = item">
                    <span> {{ item }}</span>
                    <svg v-if="activeItem == item" xmlns="http://www.w3.org/2000/svg" width="16" height="16"
                        fill="currentColor" class="bi bi-caret-right" viewBox="0 0 16 16">
                        <path
                            d="M6 12.796V3.204L11.481 8zm.659.753 5.48-4.796a1 1 0 0 0 0-1.506L6.66 2.451C6.011 1.885 5 2.345 5 3.204v9.592a1 1 0 0 0 1.659.753" />
                    </svg>
                </li>
            </ul>
        </div>
    </div>


</template>

<script>
export default {
    name: "SideBar",
    props: ['dataList'],
    data() {
        return {
            activeList: [],
            activeItem: ""
        }
    }
}
</script>

<style scoped>
#container {
    user-select: none;
    height: 100%;
    width: 100%;
    overflow-y: auto;
    overflow-x: hidden;
    padding-right: 10px;
}

p {
    display: flex;
    justify-content: space-between;
    align-items: center;
    column-gap: 10px;
    transition: all 0.5s;
    cursor: pointer;
}

#active {
    font-weight: bold;
    font-size: large;
    background-color: rgba(255, 255, 255, 0.1);
    color: green;
    transition: 0.3s;
    border-radius: 10px;
    box-shadow: 0px 0px 10px rgba(0, 0, 0, 0.2);
}

ul {
    list-style-type: none;
    padding: 0;
    display: flex;
    flex-direction: column;
    row-gap: 5px;
}

ul>li {
    padding: 10px 15px;
    font-size: 16px;
    font-weight: 400;
    cursor: pointer;
    transition: 0.3s;
    text-wrap: nowrap;
    display: flex;
    justify-content: space-between;
    align-items: center;
}

#heading {
    background-color: rgb(238, 238, 238);
    color: rgb(0, 0, 0);
    border-radius: 10px;
    padding: 10px;
    margin-bottom: 10px;
    border: 1px solid rgb(0, 0, 0);
    transition: 0.3s;
    font-size: 20px;
    font-weight: 600;
    cursor: pointer;
}


ul>li:hover {
    background-color: rgba(255, 255, 255, 0.1);
    color: white;
    transition: 0.3s;
    border-radius: 10px;
    box-shadow: 0px 0px 10px rgba(0, 0, 0, 0.2);
}

svg {
    cursor: pointer;
}
</style>