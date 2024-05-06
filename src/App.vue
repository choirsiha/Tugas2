<!-- index.vue -->
<template>
  <div>
    <h1>{{ title }}</h1>
    <input type="text" v-model="inputText" @input="updateText" placeholder="Masukkan Nama" />
    <p class="highlight" :class="{ bold: isBold }" :style="{ fontSize: textSize }">
      {{ inputText }}
    </p>
    <button @click="toggleBold">Tebalkan Tulisan</button>
    <button @click="changeTextSize">Ubah Ukuran Text</button>
  </div>
</template>

<script>
export default {
  data() {
    return {
      title: 'WELCOME',
      inputText: '',
      isBold: false,
      textSize: '18px'
    }
  },
  methods: {
    updateText(event) {
      this.inputText = event.target.value
    },
    toggleBold() {
      this.isBold = !this.isBold
    },
    changeTextSize() {
      this.textSize = this.textSize === '18px' ? '24px' : '18px'
    }
  }
}
</script>

<style>
.highlight {
  background-color: #f7f7f7;
  padding: 15px;
  border: 1px solid #ddd;
  border-radius: 10px;
  box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
  margin-bottom: 20px;
}

.highlight::before {
  content: '';
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background-color: #f7f7f7;
  transform: skewY(-5deg);
  z-index: -1;
}

.bold {
  font-weight: bold;
  font-size: 1.5em;
  color: #333;
  text-shadow: 0 1px 0 rgba(255, 255, 255, 0.5);
}

button {
  background-color: #4caf50;
  color: #fff;
  padding: 10px 20px;
  border: none;
  border-radius: 5px;
  cursor: pointer;
  box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
}

button:hover {
  background-color: #3e8e41;
}

button:active {
  transform: translateY(2px);
  box-shadow: 0 0 5px rgba(0, 0, 0, 0.2);
}
</style>
