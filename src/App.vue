<template>
  <main>
    <h1>{{ title }}</h1>
    <input type="text" ref="name" />
    <button @click="handleEvent">Click</button>
    <div class="alertDeactivate" ref="alert">
      <p>
        Die Nachricht hat gesendet: <span>{{ inputValue }}</span>
      </p>
    </div>
  </main>
</template>

<script lang="ts">
export default {
  name: "App",
  data() {
    return {
      title: "Hallo-Welt",
      inputValue: "",
    };
  },

  methods: {
    handleEvent(this: any): void {
      this.inputValue = this.$refs.name.value;
      this.$refs.alert.classList.add("alertActive");
    },
  },
};
</script>

<style lang="scss">
main {
  margin: 0 auto;
  text-align: center;
  h1 {
    font: bold 32px arial;
    text-align: center;
    margin: 68px 0;
  }
  button {
    padding: 6px 16px;
    border-radius: 4px;
    margin-left: 4px;
    border: none;
    cursor: pointer;
  }
  input {
    width: 233px;
    padding: 6px 8px;
    border-radius: 4px;
    border: none;
  }
}
.alertDeactivate {
  display: none;
}
.alertActive {
  display: flex;
  justify-content: center;
  align-items: center;
  width: 500px;
  height: 120px;
  margin: 32px auto;
  border-radius: 4px;
  background-color: #4b4b4b;
  box-shadow: 2px 2px 4px rgb(0, 0, 0, 0.1);
  p {
    font: bold 16px arial;
    color: #efefef;
    span {
      font: bold 16px arial;
      color: yellow;
    }
  }
}
</style>
