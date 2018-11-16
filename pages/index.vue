<template>
  <div class="home-page">
    <div class="green-tree text-center">
      <span>Green Tree</span>
    </div>
    <div class="center text-center">
      <h1> {{quotes[0].quote}} </h1>
    </div>
    <transition 
      name="custom-classes-transition" 
      enter-active-class="animated fadeInLeft" 
      leave-active-class="animated fadeOutLeft">
      <div @click="show=!show, showButtons=!showButtons" v-if="showButtons"  class="about-one custom-button">About</div>
    </transition>
    <transition 
      name="custom-classes-transition" 
      enter-active-class="animated zoomIn" 
      leave-active-class="animated zoomOut">
      <div v-if="show" class="about-content">
        <b-card no-body class="text-center" style="max-height=80vh;">
        <About />
          This is some text within the default card block.
          <b-btn @click="show=!show, showButtons=!showButtons" class="btn-block">Back</b-btn>
        </b-card>
      </div>
    </transition>
    <transition 
      name="custom-classes-transition" 
      enter-active-class="animated fadeInLeft" 
      leave-active-class="animated fadeOutLeft">
      <div @click="showChildren=!showChildren, showButtons=!showButtons" v-if="showButtons" class="custom-button children-button">Children</div>
    </transition>
    <transition 
      name="custom-classes-transition" 
      enter-active-class="animated zoomIn" 
      leave-active-class="animated zoomOut">
      <div v-if="showChildren" class="about-content">
        <b-card 
          title="Card Title" 
          img-src="https://picsum.photos/600/300/?image=25" 
          img-alt="Image" 
          img-top 
          tag="article"
          class="mb-2">
          <p class="card-text">
            Some quick example text to build on the card title and make up the bulk of the card's content.
          </p>
          <b-button @click="showChildren=!showChildren, showButtons=!showButtons" variant="primary">Go somewhere</b-button>
        </b-card>
      </div>
    </transition>
    <transition 
      name="custom-classes-transition" 
      enter-active-class="animated fadeInRight" 
      leave-active-class="animated fadeOutRight">
      <div @click="showThree=!showThree, showButtons=!showButtons" v-if="showButtons" class="custom-button more-button">More</div>
    </transition>
    <transition 
      name="custom-classes-transition" 
      enter-active-class="animated zoomIn" 
      leave-active-class="animated zoomOut">
      <div v-if="showThree" class="about-content">
        <b-card 
          title="Card Title" 
          img-src="https://picsum.photos/600/300/?image=25" 
          img-alt="Image" 
          img-top 
          tag="article"
          class="mb-2">
          <p class="card-text">
            Some quick example text to build on the card title and make up the bulk of the card's content.
          </p>
          <b-button @click="showThree=!showThree, showButtons=!showButtons" variant="primary">Go somewhere</b-button>
        </b-card>
      </div>
    </transition>
    <transition 
      name="custom-classes-transition" 
      enter-active-class="animated fadeInRight" 
      leave-active-class="animated fadeOutRight">
      <div @click="showSchedule=!showSchedule, showButtons=!showButtons" v-if="showButtons" class="custom-button schedule-button">Schedule</div>
    </transition>
    <transition 
      name="custom-classes-transition" 
      enter-active-class="animated zoomIn" 
      leave-active-class="animated zoomOut">
      <div v-if="showSchedule" class="about-content">
        <b-card 
          title="Card Title" 
          img-src="https://picsum.photos/600/300/?image=25" 
          img-alt="Image" 
          img-top 
          tag="article"
          class="mb-2">
          <p class="card-text">
            Some quick example text to build on the card title and make up the bulk of the card's content.
          </p>
          <b-button @click="showSchedule=!showSchedule, showButtons=!showButtons" variant="primary">Go somewhere</b-button>
        </b-card>
      </div>
    </transition>
  </div>
</template>

<script>
import About from "~/components/About.vue";

export default {
  components: {
    About
  },
  data() {
    return {
      showButtons: true,
      show: false,
      showChildren: false,
      showThree: false,
      showSchedule: false,
      quotes: [
        { quote: 'This is the first quote' },
        { quote: 'This is the second quote' },
        { quote: 'This is the third quote' },
        { quote: 'This is the fourth quote' }
      ]
    };
  },
  methods: {
    slider() {}
  }
};
</script>

<style scoped>
.home-page {
  overflow: hidden;
  width: 100%;
  position: absolute;
  top: 0px;
  bottom: 0px;
  left: 0;
  height: auto;
  background-image: url("~assets/background.jpg");
  background-size: cover;
  border: solid gray 15px;
}
.about-content {
  position: absolute;
  width: 50%;
  top: 50%;
  left: 50%;
  margin-left: -25%; /* margin is -0.5 * dimension */
  margin-top: -15%;
}
.center {
    position: absolute;
    color: white;
    width: 600px;
    height: 100px;
    top: 50%;
    left: 50%;
    margin-top: -50px;
    margin-left: -300px;
}

.green-tree {
  color: rgb(9, 88, 9);
  font-size: 7em;
}
.about-one {
  margin-left: 20px;
  position: absolute;
  left: 0;
  top: 20%;
}
.children-button {
  margin-left: 20px;
  position: absolute;
  left: 0;
  top: 70%;
}
.more-button {
  margin-right: 20px;
  position: absolute;
  right: 0;
  top: 20%;
}
.schedule-button {
  margin-right: 20px;
  position: absolute;
  right: 0;
  top: 70%;
}
.custom-button {
  border-radius: 5px;
  font-size: 2em;
  opacity: 0.4;
  text-align: center;
  color: white;
  background: black;
  width: 200px;
  height: 60px;
  border: 4px solid grey;
  transition: all .3s ease-in
}
.custom-button:hover {
  opacity: 1;
  background-color: rgb(90, 25, 1);
}
</style>
