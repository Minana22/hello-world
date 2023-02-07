<template>
  <div class="primary">
    <div class="images">
      <img v-for="n in niz" :key="n" :src="niz[brojSlike]" />
    </div>

    <div class="buttons">
      <button @click="prewPhoto" class="btn1">Preview</button>
      <button @click="pokreniGaleriju">Play</button>
      <button @click="nextPhoto">Next</button>
      <button @click="zaustaviGaleriju">Stop</button>
    </div>
  </div>
</template>
<script>
export default {
  data: function () {
    return {
      niz: [
        "https://picsum.photos/id/43/367/267",
        "https://picsum.photos/id/58/367/267",
        "https://picsum.photos/id/57/367/267",
        "https://picsum.photos/id/83/367/267",
        "https://picsum.photos/id/84/367/267",
      ],
      brojSlike: 0,
      interval: null,
      index: 0,
    };
  },
  methods: {
    pokreniGaleriju() {
      this.interval = setInterval(() => {
        this.nextPhoto();
      }, 3000);
    },
    zaustaviGaleriju() {
      clearInterval(this.interval);
    },
    prewPhoto() {
      if (this.brojSlike == 0) {
        this.brojSlike = this.niz.length - 1;
      }
      this.brojSlike -= 1;
    },

    nextPhoto() {
      if (this.brojSlike == this.niz.length - 1) {
        this.brojSlike = 0;
      }
      this.brojSlike += 1;
    },
  },
};
</script>

<style>
.images {
  width: 400px;
  height: 400px;
  display: flex;
  overflow: hidden;
}
.primary {
  background-color: rosybrown;
  display: flex;
  justify-content: center;
  flex-direction: column;
  align-items: center;
}
.buttons {
  padding: 5px 10px;
}
.btn1 {
  width: 70px;
  height: 30px;
  margin-right: 5px;
  color: rgb(2, 54, 54);
  background-color: rgb(9, 240, 240);
  cursor: pointer;
}
.btn2 {
  width: 70px;
  height: 30px;
  margin-right: 5px;
  color: rgb(28, 2, 2);
  background-color: rgb(180, 20, 167);
}
.btn3 {
  width: 70px;
  height: 30px;
  margin-right: 5px;
  color: rgb(2, 54, 54);
  background-color: rgb(17, 236, 236);
}
</style>
