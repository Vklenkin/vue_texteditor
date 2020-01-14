<template>
  <div>
    <label for="fontSizeInput" class="label-pa">Размер</label> 
      <select 
        style="font-size: 12pt"
        v-on:input="$emit('change-font-size', $event)"
        id="fontSizeInput"
        name="fontSizeInput"
      >
        <option value="8"  style="font-size: 8pt" > 8</option>
        <option value="9"  style="font-size: 9pt" > 9</option>
        <option value="10" style="font-size: 10pt"> 10</option>
        <option value="11" style="font-size: 11pt"> 11</option>
        <option value="12" style="font-size: 12pt"> 12</option>
        <option selected value="14" style="font-size: 14pt"> 14</option>
        <option value="16" style="font-size: 16pt"> 16</option>
        <option value="18" style="font-size: 18pt"> 18</option>
        <option value="20" style="font-size: 20pt"> 20</option>
        <option value="22" style="font-size: 22pt"> 22</option>
        <option value="24" style="font-size: 24pt"> 24</option>
        <option value="26" style="font-size: 26pt"> 26</option>
        <option value="28" style="font-size: 28pt"> 28</option>
        <option value="36" style="font-size: 36pt"> 36</option>
        <option value="48" style="font-size: 48pt"> 48</option>
        <option value="72" style="font-size: 72pt"> 72</option>
      </select>
  </div>
</template>

<script>
export default {
  name: "FontSizeInput"
};
</script>

<style scoped>
select {
  width: 55px;
  margin-top: 15px;
}
</style>
