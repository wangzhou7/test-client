<template>
  <div id="app">
    <Header id="header"></Header>
    <main id="main">
      <router-view />
    </main>
    <Footer id="footer"></Footer>
  </div>
</template>

<script>
import Header from './components/header.vue';
import Footer from './components/footer.vue';

export default {
  name: 'App',
  components:{ Header,Footer }
}
</script>


<style lang="less">

@import "./assets/common.less";

html, body, #app{
  height: 100%;
}

#app {
  display: grid;
  grid-template-columns: 10% auto 10%;
  grid-template-rows: auto 1fr auto;
  grid-template-areas: "header header header"
                       ".      main  ."
                       "footer footer footer";

  #header {
    grid-area: header;
    padding-left: 12%;
    padding-right: 12%;
  }

  #main {
    grid-area: main;
  }

  #footer {
    grid-area: footer;
    padding-left: 12%;
    padding-right: 12%;
  }

}

@media (max-width: 768px) {
  #app {
    grid-template-columns: 10px auto 10px;

    #header, #footer {
      padding-left: 10px;
      padding-right: 10px;
    }
  }

}



</style>

