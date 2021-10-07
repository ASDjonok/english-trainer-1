<template>
  <div class="container">
    <p class="row">Your score is&nbsp<b>{{ score }}</b></p>
    <p class="row">Please, provide a translation for sentence:</p>
    <p><b>{{ translation }}</b></p>
    <div class="row words-control">
      <div v-for="(word,index) in randomSequence">
        <b-button v-on:click="wordClicked(index)" variant="outline-primary">{{ word }}</b-button>
        &nbsp
      </div>
    </div>

    <br/>
    <p>Guessed in current sentence&nbsp<b>{{ expectedWordIndex }}</b></p>

    <div class="row">
      <div class="collected words" v-for="item in collectedSequence">
        <b-button variant="success">{{ item }}</b-button>
        &nbsp
      </div>
    </div>

    <b-toast id="winner-toast" variant="warning" solid>
      <template #toast-title>
        <div class="d-flex flex-grow-1 align-items-baseline">
          <b-img blank blank-color="#ff5555" class="mr-2" width="12" height="12"></b-img>
          <strong class="mr-auto">Congatulation</strong>
        </div>
      </template>
      You gathered word, now your score is {{ score }}
    </b-toast>
  </div>
</template>

<script>
import {sentences, translations} from './base.js'

export default {
  name: "exercices",
  data() {
    return {
      score: 0,
      sentence: "I have two cups",
      translation: "У меня есть два стакана",
      correctSequence: [],
      randomSequence: ["I", "two", "cups", "have"],
      collectedSequence: [],
      expectedWordIndex: null,
    }
  },
  methods: {
    wordClicked(index) {
      console.log(this.randomSequence[index])
      if (this.correctSequence[this.expectedWordIndex] === this.randomSequence[index]) {
        this.collectedSequence[this.expectedWordIndex] = this.correctSequence[this.expectedWordIndex]
        this.expectedWordIndex++
        console.log(this.collectedSequence)

        if (this.expectedWordIndex === this.correctSequence.length) {
          this.score++
          this.$bvToast.show('winner-toast')
          this.nextSentence()
        }
      }

    },
    prepareLists() {
      this.correctSequence = this.sentence.toLowerCase().split(" ")
      this.randomSequence = this.shuffleArray(this.correctSequence)
      this.collectedSequence = []
      this.expectedWordIndex = 0
      console.log(this.correctSequence)
      console.log(this.randomSequence)
    },

    nextSentence() {
      const randonIndex = Math.floor(Math.random() * (sentences.length ))
      console.log(randonIndex)
      this.translation = translations[randonIndex]
      this.sentence = sentences[randonIndex]
      this.prepareLists()
    },

    /* Randomize array in-place using Durstenfeld shuffle algorithm */
    shuffleArray(array) {
      let rez = [...array]
      for (var i = rez.length - 1; i > 0; i--) {
        var j = Math.floor(Math.random() * (i + 1))
        var temp = rez[i]
        rez[i] = rez[j]
        rez[j] = temp
      }
      return rez
    }
  },
  created() {
    console.log(sentences)
    this.nextSentence()
  }
}
</script>

<style scoped>

</style>
