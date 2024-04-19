<template>
  <div class="container">
    <div class="title box-decorator">Vue Playground</div>
    <div class="main">
      <aside class="box-decorator">
        <SideBar :data-list="dataList"/>
      </aside>
      <main class="box-decorator">
        main
      </main>
    </div>
  </div>

</template>

<script>
import SideBar from './components/Aside.vue';

export default {
  name: "App",
  components: {
    SideBar,
  },
  data() {
    return {
      activeTab:"",
       dataList : [
        {
          category: "Basic",
          items: [
            "Hello World",
            "Handling User Input",
            "Attribute Bindings",
            "Conditionals and Loops",
            "Form Bindings",
            "Simple Component"
          ]
        },
        {
          category: "Practical",
          items: [
            "Markdown Editor",
            "Fetching Data",
            "Grid with Sort and Filter",
            "Tree View",
            "SVG Graph",
            "Modal with Transitions",
            "List with Transitions",
            "TodoMVC"
          ]
        },
        {
          category: "7 GUIs",
          items: [
            "Counter",
            "Temperature Converter",
            "Flight Booker",
            "Timer",
            "CRUD",
            "Circle Drawer",
            "Cells"
          ]
        }
      ]
    }
  }

}



</script>

<style scoped>
.container {
  margin: auto;
  height: 90vh;
  width: 80vw;
  display: flex;
  justify-content: center;
  align-items: center;
  flex-direction: column;
}

.main {
  margin: auto;
  height: 80%;
  width: 80vw;
  display: flex;
  justify-content: center;
  align-items: center;
  column-gap: 20px;
}

.box-decorator {
  background: var(--color-9);
  border-radius: 10px;
  padding: 15px;
  box-shadow: 0 0 1px 1px;
}

aside {
  width: 20%;
  height: 100%;
}

main {
  width: 80%;
  height: 100%;
}

.title {
  width: 100%;
  height: 10%;
  display: flex;
  justify-content: center;
  align-items: center;
  padding: 5px 0;
  font-size: 2.5rem;
  font-weight: bold;
  color: aliceblue;
  background: var(--color-9);

}
</style>