<template>
  <div>
      <input @input="onChange"/>
  </div>
</template>

<script>
export default {
    name: 'SearchInput',
    methods:{
        onChange: function(event) {
            // const term = event.target.value
            this.$emit('newTerm', event.target.value)
        }
    }
}
</script>

<style>

</style>