<template>
  <div class="wrapper">
    <input v-model="result" class="input" type="text" />
    <div class="buttoms">
      <div
        @click="mathValue(num)"
        class="dop numbers"
        v-for="num in numbers"
        :key="num"
      >
        {{ num }}
      </div>
      <div
        @click="mathValue(op)"
        class="dop operations"
        v-for="op in operations"
        :key="op"
      >
        {{ op }}
      </div>
      <div @click="mathClear" class="dop operations">R</div>
      <div @click="mathEquals" class="dop operations">=</div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      result: "",
      numbers: [1, 2, 3, 4, 5, 6, 7, 8, 9, 0],
      operations: ["+", "-", "/", "*"],
    };
  },
  methods: {
    mathValue(va) {
      this.result += va;
    },
    mathClear() {
      this.result = "";
    },
    mathEquals() {
      this.result = eval(this.result);
    },
  },
};
</script>

<style>
.wrapper {
  width: 200px;
}
.input {
  width: 100%;
  height: 20px;
  text-align: right;
}
.buttoms {
  display: flex;
  flex-wrap: wrap;
  justify-content: space-around;
  width: 100%;
}
.dop {
  display: flex;
  flex: 33%;
  height: 50px;
  justify-content: center;
  align-items: center;
  cursor: pointer;
  font-size: 18px;
}

.numbers {
  font-size: 18px;
  background-color: rgb(2, 81, 105);
}
.numbers:hover {
  background-color: rgb(1, 47, 61);
}

.operations {
  background-color: rgb(32, 192, 152);
}
.operations:hover {
  background-color: rgb(22, 138, 109);
}
</style>
