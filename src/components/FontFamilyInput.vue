<template>
  <div class="container" >
    <label for="fontFamilyInput" class="label-pa">Шрифт</label>
    <select
      style="font-size: 12pt"
      v-on:input="$emit('change-font-family', $event)"
      id="fontFamilyInpout"
      name="fontFamilyInput"
    >
      <option>Arial, Helvetica, sans-serif</option>
      <option>Lucida Console, Monaco, monospace</option>
      <option>Times New Roman, Times, serif</option>
      <option>Comic Sans MS, cursive</option>
    </select>
  </div>
</template>

<script>
export default {
  name: "fontFamilyInput"
};
</script>

<style scoped>
select {
  margin-top: 15px;
}
.container {
  flex-direction: row;
}
</style>
