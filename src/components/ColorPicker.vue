<template>
  <div>
    <label for="colorChange" class="label-pa">Цвет</label>
    <input
      type="color"
      list="presetColors"
      value="#000000"
      id="colorChange"
      name="colorChange"
      v-on:change="$emit('change-color', $event)"
    />
    <datalist id="presetColors">
      <option value="#008080"/>
      <option value="#191970"/>
      <option value="#4B0082"/>
      <option value="#FF4500"/>
      <option value="#FFD700"/>
    </datalist>
  </div>
</template>

<script>
export default {
  name: "ColorPicker"
};
</script>

<style scoped>
input {
  width: 50px;
  height: 24px;
  margin-top: 10px;
}
</style>
