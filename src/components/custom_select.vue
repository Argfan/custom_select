<template>
  <div class="select">
    <div 
      class="title"
      @click="isOpen = !isOpen"
    > {{ selected }} </div>
    <div 
      v-if="isOpen"
      class="optionBlock"
    >
      <div 
        v-for="option in options"
        :key="option.value"
        class="option"
        :class="{ active: activeCheck(option) }"
        @click="selectOption(option)"
      >
        {{ option.name }}
      </div>
    </div>
    
  </div>
</template>
<script>
export default {
  name: "custom-select",
  props: {
    options: {
      type: Array,
      default: () => []
    },
    selected: {
      type: [String],
      default : ''
    }
  },
  data(){
    return{
      isOpen: false
    }
  },
  computed:{
    // activeCheck(){

    // }
  },
  methods: {
    selectOption(option){
      this.$emit('selectOption', option)
      this.isOpen = false
    },
    activeCheck(opton){
      return opton.name == this.selected
    }
  }
}
</script>
<style lang="scss" scoped>
  .select{
    min-width: 150px;
    position: relative;
    cursor: pointer;
    .title{
      padding: .3rem 1rem;
      border: 1px solid #ddd;
    }
    .optionBlock{
      position: absolute;
      top: 100%;
      left: 0;
      width: 100%;
      border: 1px solid #ddd;
      .option{
        padding: 5px 15px;
        transition: .2s;
        &:hover{
          background-color: #eee;
        }
        &.active{
          background-color: rgb(38, 91, 235);
          color: #fff;
        }
        
      }
    }
  }
</style>