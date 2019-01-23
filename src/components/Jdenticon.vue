<template>
  <div>
    <div>
      Input:
      <input @input="onInput" />
    </div>

    <div>
        Output:
        <div v-html="identicon" />
    </div>
  </div>
</template>

<script>
  import jd from 'jdenticon'

  export default {
    name: 'Jdenticon',
    data: () => {
      return {
        textInput: '',
      }
    },
    // .data
    methods: {
      onInput(e) {
        this.textInput = e.target.value
      }
    },// .methods
    computed: {
      identicon() {
        return jd.toSvg(this.textInput, 200);
      },
    }, // .computed
  }// .export

</script>

<style>
</style>
