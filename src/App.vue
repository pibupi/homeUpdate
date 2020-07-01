<template>
  <div id="app">
    <Header />
    <!-- <Card>
      <div style="min-height: 600px;">
        <Carousel v-model="value1" height:500px loop>
          <CarouselItem>
            <img src="./assets/u11.jpg" alt="" width="100%" height="400" />
          </CarouselItem>
          <CarouselItem>
            <img src="./assets/u11.jpg" alt="" width="100%" height="400" />
          </CarouselItem>
          <CarouselItem>
            <img src="./assets/u11.jpg" alt="" width="100%" height="400" />
          </CarouselItem>
          <CarouselItem>
            <img src="./assets/u11.jpg" alt="" width="100%" height="400" />
          </CarouselItem>
        </Carousel>
      </div>
    </Card> -->
    <!-- <Side-menu /> -->
  </div>
</template>

<script>
// import HelloWorld from './components/HelloWorld.vue'
// import SideMenu from './menu'
import Header from './header/index'

export default {
  name: 'App',
  components: {
    // HelloWorld,
    // SideMenu,
    Header,
  },
  data() {
    return {
      value1: 0,
    }
  },
}
</script>

<style>
li,
ul,
html,
header,
section,
body {
  padding: 0;
  margin: 0;
}
li {
  list-style: none;
}
#app {
  background-color: #ccc;
  /* font-family: Avenir, Helvetica, Arial, sans-serif; */
  /* -webkit-font-smoothing: antialiased; */
  /* -moz-osx-font-smoothing: grayscale; */
  /* text-align: center;
  color: #2c3e50;
  margin-top: 60px; */
}
.img1 {
  width: 100%;
  height: 300px;
}
.demo-carousel {
  /* margin-top: 100px; */
  height: 400px;
  line-height: 430px;
  text-align: center;
  color: #fff;
  font-size: 20px;
  background: #506b9e;
}
#app >>> .ivu-card-body {
  padding: 0;
}
</style>
