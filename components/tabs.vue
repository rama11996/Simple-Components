<template lang="pug">
.tabs
  .tab-details(v-for="item in tabs" :class="{ active: isCurrent(item)}")
    .name
      a(@click="open(item)") {{ item.name }}
    .details {{ item.content }}  
</template>
<script>
export default {
  data (){
    return{
      tabs: [
        { id: 1, name:'Chennai', content:'Capital of Tamil Nadau' },
        { id: 2, name:'Banagalore', content:'Capital of Karanataka'},
        { id: 3, name:'Tiruvandrum', content:'Capital of kerala'}
      ],
      opened: null
    }
  },
  methods:{
    open (item) {
       this.opened = this.isCurrent(item) ? null : item
    },
    isCurrent (item) {
       return this.opened && this.opened.id === item.id
    }
  }
}
</script>
<style lang="sass" scoped>
.tabs
  display: flex
  .tab-details
    display: flex
    flex-direction: column
    margin-left: 1rem
    .name
      border: 1px solid 
      border-radius: 1rem
      a
        background: green  
        font-size: 3rem
        cursor: pointer
    .details
      font-size: 2rem 
      display: none   
  .tab-details.active
    .name
      a
        background: orange
    .details
      display: block    
</style>


