<script setup>
import { ref } from 'vue';

let notify = ref(2)
function addValue() {
  notify.value++
  console.log(notify)
}

function minValue() {
  if (notify.value > 0) {
    notify.value--
  }
}
</script>

<template>
  <div class="wrapper">
    <div class="profile">

      <div class="ballon" v-show="notify > 0">{{ notify }}</div>
    </div>
    <div class="button-wrapper">
      <div class="button" @click="addValue">+</div>
      <div class="button" @click="minValue">-</div>
    </div>
    <div v-if="notify > 0"><strong>Me escribieron 😍</strong></div>
    <div v-else>Nadie me escribe 😢</div>
  </div>
</template>

<style scoped>
.button {
  background-color: beige;
  display: inline-block;
  padding: 5px 0;
  border-radius: 6px;
  width: 40px;
  margin: 0 8px;
}

.button:hover {
  cursor: pointer;
  background-color: #D8B08C;
}

.ballon {
  position: absolute;
  top: 0;
  right: 0;
  width: 32px;
  height: 32px;
  background-color: #D8B08C;
  border-radius: 100%;
  display: flex;
  justify-content: center;
  align-items: center;
  color: white;
}

.profile {
  background-image: url('https://www.eluniverso.com/resizer/z9_nKwhsX_E71gVvaZwBsed-M8I=/arc-anglerfish-arc2-prod-eluniverso/public/L7PEDR6HJVHHZGER63DAES6XBQ.png');
  background-size: cover;
  position: relative;
  background-color: #D2E8E3;
  width: 120px;
  height: 120px;
  margin: 0 auto;
  border-radius: 100%;
}

.wrapper {
  text-align: center;
  padding-top: 18px;
  background-color: #0F6466;
  width: 60%;
  border-radius: 12px;
  margin: 0 auto;
  overflow: hidden;
  margin-bottom: 16px;
}

.button-wrapper {
  margin-top: 16px;
  margin-bottom: 16px;


}
</style>
