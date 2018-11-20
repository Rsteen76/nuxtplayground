<template>
  <div class="home-page">
    <img src="~/assets/GreenTreeLogo.png" class="center text-center" v-if="showButtons"/>
    <transition 
      name="custom-classes-transition" 
      enter-active-class="animated fadeInLeft" 
      leave-active-class="animated fadeOutLeft">
      // Home Button
      <img src="~assets/ButtonHome.png" @click="show=!show, showButtons=!showButtons" v-if="showButtons"  class="about-button custom-button"/>
    </transition>
    <transition 
      name="custom-classes-transition" 
      enter-active-class="animated zoomIn" 
      leave-active-class="animated zoomOut">
      <div v-if="show" class="about-content">
        <b-card no-body class="text-center">
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
      <img src="~assets/ButtonKids.png" @click="showChildren=!showChildren, showButtons=!showButtons" v-if="showButtons" class="custom-button children-button"/>
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
          class="mb-2 scroll">
          <p class="card-text">
            Some quick example text to build on the card title and make up the bulk of the card's content.  Some quick example text to build on the card title and make up the bulk of the card's content. Some quick example text to build on the card title and make up the bulk of the card's content.  Some quick example text to build on the card title and make up the bulk of the card's content.  Some quick example text to build on the card title and make up the bulk of the card's content. Some quick example text to build on the card title and make up the bulk of the card's content. Some quick example text to build on the card title and make up the bulk of the card's content.  Some quick example text to build on the card title and make up the bulk of the card's content. Some quick example text to build on the card title and make up the bulk of the card's content.  Some quick example text to build on the card title and make up the bulk of the card's content.  Some quick example text to build on the card title and make up the bulk of the card's content. Some quick example text to build on the card title and make up the bulk of the card's content.
          </p>
          <b-button @click="showChildren=!showChildren, showButtons=!showButtons" variant="primary">Go somewhere</b-button>
        </b-card>
      </div>
    </transition>
    <transition 
      name="custom-classes-transition" 
      enter-active-class="animated fadeInRight" 
      leave-active-class="animated fadeOutRight">
      <img src="~/assets/ButtonInfo.png" @click="showThree=!showThree, showButtons=!showButtons" v-if="showButtons" class="custom-button more-button"/>
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
      <img src="~assets/ButtonCalendar.png" @click="showSchedule=!showSchedule, showButtons=!showButtons" v-if="showButtons" class="custom-button schedule-button"/>
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
  font-family: 'Oxygen', sans-serif;
  overflow: hidden;
  width: 100%;
  position: absolute;
  top: 0px;
  bottom: 0px;
  left: 0;
  height: auto;
  background-image: url("~assets/GreenTreeBG.jpg");
  background-size: cover;
}
.about-content {
  position: absolute;
  width: 50%;
  height: 80%;
  top: 50%;
  left: 50%;
  margin-left: -25%; /* margin is -0.5 * dimension */
  margin-top: -22%; 
}
.center {
  position: relative;
  top: 50%;
  transform: translateY(-60%);
  display: block;
  margin: auto;
  width: 20%;
  min-width: 300px;
}

.green-tree {
  color: rgb(47, 170, 47);
  font-size: 7em;
}
.about-button {
  margin-left: 0px;
  position: absolute;
  left: 0;
  top: 0;
}
.children-button {
  margin-left: 0px;
  margin-bottom: 0;
  position: absolute;
  left: 0;
  bottom: 0;
}
.more-button {
  margin-right: 0px;
  position: absolute;
  right: 0;
  top: 0;
}
.schedule-button {
  margin-right: 0px;
  position: absolute;
  right: 0;
  bottom: 0;
}
.custom-button {
  padding-top: 0px;
  font-size: 2em;
  text-align: center;
  color: rgb(255, 251, 251);
  width: 15%;
  max-width: 150px;
  height: auto;
  transition: all .3s ease-in;
  z-index: 1
}
.custom-button:hover {
  text-decoration: underline;
}
.custom-button::after {
  background-color: yellow;
}
.scroll {
  max-height: 90%;
    overflow-y: auto;
}
@media only screen and ( max-width: 800px ) {
  .custom-button {
    min-width:30%;
    transition: all .3s ease-in
  }
  
  .green-tree {
    color: rgb(47, 170, 47);
    top: 30px;
    font-size: 3.75em;
  }
.center {
  position: relative;
  top: 50%;
  transform: translateY(-60%);
  display: block;
  margin: auto;
  width: 40%;
  min-width: 300px;
}
  .about-content {
    position: absolute;
    width: 90%;
    height: 90%;
    top: 50%;
    left: 50%;
    margin-left: -45%; /* margin is -0.5 * dimension */
    margin-top: -55%;
  }
  .scroll {
    max-height: 350px;
    overflow-y: auto;
}
}

</style>
