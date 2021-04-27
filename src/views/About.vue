<template>
  <div class="about">
    <h1>Min</h1>
    <input v-model.number="minA">
    <input v-model.number="minB">
    <button v-on:click="min()">Min</button>
    {{ minAnswer }}
    <h1>Max</h1>
    <input v-model.number="maxA">
    <input v-model.number="maxB">
    <button v-on:click="max()">Max</button>
    {{ maxAnswer }}
    <h1>Abs</h1>
    <input v-model.number="absA">
    <button v-on:click="abs()">Return abs number</button>
    {{ absAnswer }}
    <h1>isEven?</h1>
    <input v-model.number="isEvenA">
    <button v-on:click="isEven()">Return if even.</button>
    {{ isEvenAnswer }}
  </div>
</template>
<script>

function isEven() {
  if(this.isEvenA % 2 === 0){
    this.isEvenAnswer = 'Is even!'
  } else{
    this.isEvenAnswer = 'Is NOT even!'
  }

}

function abs() {
  if(this.absA < 0){
    this.absAnswer = this.absA * (-1);
  } else{
    this.absAnswer = this.absA;
  }

}

function min() {
  if (this.minA < this.minB) {
    this.minAnswer = this.minA;
  } else {
    this.minAnswer = this.minB;
  }
}

function max(){
  if (this.maxA<this.maxB){
    this.maxAnswer = this.maxB
  } else {
    this.maxAnswer = this.maxA
  }

}


export default {
  data: function () {
    return {
      'minA': 0,
      'minB': 0,
      'minAnswer': 0,
      'maxA': 0,
      'maxB': 0,
      'maxAnswer': 0,
      'absA':0,
      'absAnswer': 0,
      'isEvenA' : 0,
      'isEvenAnswer': 0,
    }
  },
  methods: {
    'min': min,
    'max': max,
    'abs': abs,
    'isEven': isEven,
  }
}
</script>