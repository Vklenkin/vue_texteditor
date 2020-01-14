<template>
  <textarea
    id="TextareaResize"
    name="text"
    placeholder="Введите ваш текст"
    v-model="val"
    v-on:input="resize"
    v-bind:style="{
      lineHeight: lineHeight + 'px',
      height: height,
      color: textColor,
      fontSize: fontSize + 'px',
      fontFamily: fontFamily,
      overflowY: overflow
    }"
  ></textarea>
</template>

<script>
export default {
  name: "TextareaResize",
  props: {
    fontSize: Number,
    maxRows: Number,
    textColor: String,
    fontFamily: String
  },
  data() {
    return {
      val: "",
      lineHeight: this.fontSize,
      height: "25px",
      overflow: "hidden"
    };
  },
  methods: {
    resize() {
      this.lineHeight = this.fontSize;
      this.maxHeight = this.maxRows * this.lineHeight +5;
      this.height = "0px";
      this.$nextTick(() => {
        if (this.$el.scrollHeight > this.maxHeight) {
          this.height = this.maxHeight + "px";
          this.overflow = "scroll";
        } else {
          this.height = this.$el.scrollHeight + "px";
          this.overflow = "hidden";
        }
      });
    }
  },
  watch: {
    fontFamily: function() {
      this.resize();
    },
    fontSize: function() {
      this.resize();
    }
  }
};
</script>

<style scoped>
textarea {
  resize: none;
  width: 90%;
  align-self: center;
  margin-top: 20px;
  display: flex;
}
</style>
