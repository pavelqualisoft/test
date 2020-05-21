<template>
  <div>
    <div class="question">{{ question.title }}</div>
    <hr>
    <div class="ansvers">
      <label v-for="(ansver, index) in question.ansvers" :key="index">
        <!-- <input :type="question.type" :name="ansver.name" :value="ansver.value" @change="checkInput($event)"> -->
        <input :type="question.type" :name="ansver.name" :value="ansver.value" v-model="vars[ansver.name]">
        {{ ansver.text }} - {{ vars }}
      </label>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    question: Object
  },
  data() {
    return {
      vars: {}
    }
  },
  methods: {
    checkInput(event) {
      this.$emit('check-input', event.target);
    },
  },
}
</script>