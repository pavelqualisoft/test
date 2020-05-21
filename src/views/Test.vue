<template>
  <div class="test">
    <h2>Test</h2>
    <hr>
    <question :question="questions[position]"
      @check-input="checkingInput"
    ></question>
    <hr>
    <button class="btn btn__next">Далее</button>
  </div>
</template>

master change

<script>
// @ is an alias to /src
// import HelloWorld from "@/components/HelloWorld.vue";
import Question from "@/components/Question.vue";

export default {
  name: "Test",
  components: {
    Question
  },
  data() {
    return {
      userAnswers: [],
      position: 0,
      questions: [
        {
          type: 'radio',
          title: 'Какой тег задаёт ссылку?',
          ansvers: [
            {
              name: 'teg',
              value: 'a',
              text: 'a'
            },
            {
              name: 'teg',
              value: 'div',
              text: 'div'
            },
            {
              name: 'teg',
              value: 'span',
              text: 'span'
            },
            {
              name: 'teg',
              value: 'img',
              text: 'img'
            },
          ]
        },
      ]
    };
  },
  methods: {
    checkingInput(target) {
      var aData = {};
      aData[target.value] = target.checked;
      // this.userAnswers.splice(this.position, 1, aData);
      // if (typeof this.userAnswers[this.position] == 'undefined') {
        this.userAnswers[this.position] = aData;
      // }
      // this.userAnswers.splice(this.position, 1, aData);
      console.log(this.userAnswers);
    }
  },
};
</script>

<style lang="scss">
.test {
  text-align: left;
  max-width: 1280px;
  margin: 0 auto;

  h2 {
    text-align: center;
    text-transform: uppercase;
  }

  label {
    display: block;
  }
}
</style>