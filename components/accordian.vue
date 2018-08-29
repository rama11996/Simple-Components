<template lang="pug">
.accordian
  label(v-for="item in accord")
    span {{ item.header }}
    input(name="accord" type="checkbox", :value="item.id")
    div {{ item.detail }} 

</template>
<script>
export default {
  data() {
    return {
      accord: [
        { id: 1, header: 'Section 1', detail:'11111 Lorem ipsum dolor sit amet, consectetur adipiscing elit. Morbi in interdum neque. Etiam dignissim volutpat lobortis. Pellentesque et rhoncus mi, ut elementum nulla.' },
        { id: 2, header: 'Section 2', detail:'22222 Lorem ipsum dolor sit amet, consectetur adipiscing elit. Morbi in interdum neque. Etiam dignissim volutpat lobortis. Pellentesque et rhoncus mi, ut elementum nulla.' },
        { id: 3, header: 'Section 3', detail:'33333 Lorem ipsum dolor sit amet, consectetur adipiscing elit. Morbi in interdum neque. Etiam dignissim volutpat lobortis. Pellentesque et rhoncus mi, ut elementum nulla.' }
      ],
    }   
  }
}
</script>

<style lang="sass" scoped>
.accordian
  label
    input[type="checkbox"],
    input[type="radio"]
      display: none
    span
      display: block
      background: crimson
      color: #FFFFFF
      padding: 1rem
    div
      display: none
    input:checked + div
      display: block
</style>

