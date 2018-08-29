<template lang="pug">
.accordian
  .content(v-for="item in accord", :class="{ active: isCurrent(item)}")
    header(@click="select(item)")   
      a {{ item.header }}
    main.pannel {{ item.detail }}

</template>
<script>
export default {
  data() {
    return {
      accord: [
        { id: 1, header: 'Section 1', detail:'Lorem ipsum dolor sit amet, consectetur adipiscing elit. Morbi in interdum neque. Etiam dignissim volutpat lobortis. Pellentesque et rhoncus mi, ut elementum nulla.' },
        { id: 2, header: 'Section 2', detail:'Lorem ipsum dolor sit amet, consectetur adipiscing elit. Morbi in interdum neque. Etiam dignissim volutpat lobortis. Pellentesque et rhoncus mi, ut elementum nulla.' },
        { id: 3, header: 'Section 3', detail:'Lorem ipsum dolor sit amet, consectetur adipiscing elit. Morbi in interdum neque. Etiam dignissim volutpat lobortis. Pellentesque et rhoncus mi, ut elementum nulla.' }
      ],
      selected: null,
    }   
  },
  methods: {
    select (item) {
      this.selected = this.isCurrent(item) ? null : item
      console.log(this.selected)
    },
    isCurrent (item) {
      return this.selected && this.selected.id === item.id
    
    }
  },
  mounted () {
    // this.selected = this.accord[0]
  }
  
}
  

</script>
<style lang="sass" scoped>
.accordian
  margin: 1rem
  width: 50%
  header
    background: #F96
    padding: 1rem
    font-weight: bold
    a
      display: block
      cursor: pointer
  main
    padding: 1rem
    display: none

  .content.active
    border: 1px solid
    margin: 20px
    header
      background: #f90
    main
      display: block
      
</style>

