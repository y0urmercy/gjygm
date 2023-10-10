<template>
<div>
  <div :class="{'active': isActive, 'disabled': !isActive}">test</div>
  <button @click="isActive = !isActive">click</button>
  <div :style="customStyles">hhhhh</div>
  <button :class="buttonClass" @click="change">{{buttonText}}</button>
</div>
<div :class="'progress'">
  <div :style="progressStyles"></div>
</div>
<button @click="changepr(10)">10</button>
<button @click="changepr(40)">40</button>
<button @click="changepr(90)">90</button>
</template>

<script>

export default {
  name: 'App',
  data(){
    return {
      isActive: false,
      buttonText: "click",
      progress: 50,
    }
  },
  computed: {
    customStyles() {
      return {
        backgroundColor: 'green',
        color: 'white',
        fontSize: '16px'
      }
    },
    buttonClass(){
      return {
        'active': this.isActive,
        'disabled': !this.isActive
      }
    },
    progressStyles(){
      return {
        width: this.progress + '%',
        backgroundColor: 'blue',
      }
    },

  },
  methods: {
    change(){
      this.isActive = !this.isActive;
    },
    changepr(numProgress){
      this.progress = numProgress;
    }
  }
}
</script>

<style>
.active {
  background-color: red;
}

.disabled {
  opacity: 0.5;
  cursor: not-allowed;
}

.progress{
  width: 100%;
  height: 20px;
  background-color: lightgreen;
}
.progress > div {
  height: 100%;
}
</style>
