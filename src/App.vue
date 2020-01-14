<template>
  <div id="app">
    <div class="settingsTextPanel">
      <FontFamilyInput v-on:change-font-family="fontFamily= $event.target.value" />
      <FontSizeInput v-on:change-font-size="changeFontSize($event.target.value)" />
      <ColorPicker v-on:change-color="textColor = $event.target.value" />
    </div>
    <TextareaResize
      v-bind:fontFamily="fontFamily"
      v-bind:textColor="textColor"
      v-bind:fontSize="fontSize"
      :maxRows="10"
    />
  </div>
</template>

<script>
import ColorPicker from "./components/ColorPicker.vue";
import FontSizeInput from "./components/FontSizeInput.vue";
import FontFamilyInput from "./components/FontFamilyInput.vue";
import TextareaResize from "./components/TextareaResize.vue";

export default {
  name: "app",
  components: {
    ColorPicker,
    FontSizeInput,
    FontFamilyInput,
    TextareaResize
  },
  data() {
    return {
      textColor: "black",
      fontFamily: "Arial, Helvetica, sans-serif",
      fontSize: 14
    };
  },
  methods: {
    changeFontSize(value) {
     
      this.fontSize = +value;
    }
  }
};
</script>

<style>
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #112519;
  display: flex;
  justify-content: center;
  align-content: center;
}

.settingsTextPanel {
  display: flex;
  flex-wrap: nowrap;
  justify-content: center;
  align-self: center;
  align-content: center;
  height: 50px;
  min-width: 90%;
}

.settingsTextPanel > div {
  margin-bottom: 20px;
}

.label-pa{
  padding: 0 5px;
}

#app {
  flex-direction: column;
  width: 100%;
  margin: 0 auto;
  margin-top: 60px;
  align-items: flex-start;
  flex-wrap: wrap;
}

.settingsTextPanel:nth-child(2) {
  margin-bottom: 20px;
}
</style>
