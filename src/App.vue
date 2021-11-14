<template>
  <div id="app">
    <div class="block">
      <custom-select
        :options="options"
        :selected="selected"
        @selectOption="selectOption"
      />
    </div>
    
  </div>
</template>

<script>

import customSelect from './components/custom_select.vue'

export default {
  name: 'App',
  components: {
    customSelect
  },
  data(){
    return{
      options: [
        {name: 'option1', value: 1},
        {name: 'option2', value: 2},
        {name: 'option3', value: 3},
        {name: 'option4', value: 4},
        {name: 'option5', value: 5},
      ],
      selected: "Выберите"
    }
  },
  methods: {
    selectOption(option){
      this.selected = option.name
    }
  }
}
</script>

<style lang="scss">
*{box-sizing: border-box;}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
  margin-top: 60px;
  padding: 15px;
  .block{
    width: 150px;
  }
}
</style>
