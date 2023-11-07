<script>
import { TEST } from "@/test/test";
import router from "@/router";
import axios from "axios";
import Loader from "@/components/Loader.vue";

export default {
  components: { Loader },
  data() {
    return {
      questions: [],
      question: {},
      results: 0,
      numberQuestion: 1,
      viewNumberQuestion: 1,
      humanAnswer: "",
      isDisabled: false,
      isCorrect: true,
      isLoad: false
    }
  },
  methods: {
    initQuestions() {
      TEST.forEach(e => {
        const categories = e['categories']
        categories.forEach(elem => {
          const questions = elem['questions']
          questions.forEach(element => {
            element['block'] = e['block']
            element['category'] = elem['category']
          })
          this.questions.push(...questions)
        })
      })
    },
    setQuestion(data) {
      this.question = data
    },
    checkCorrectAnswer(value) {
      if (this.question['block'] === 3) { return value === this.question['correct_answer'] && this.humanAnswer.length !== 0 }
      return this.humanAnswer === value && this.humanAnswer === this.question['correct_answer']
    },
    checkIncorrectAnswer(value) {
      if (this.question['block'] === 3) { return value === this.humanAnswer && value !== this.question['correct_answer'] }
      return this.humanAnswer !== value || this.humanAnswer !== this.question['correct_answer']
    },
    checkDefaultAnswer(value) {
      if (this.question['block'] === 3) {
        return false
      }
      return this.humanAnswer !== value || this.humanAnswer.length === 0
    },
    async nextQuestion() {
      if (this.isCorrect) {
        this.results += +this.question['category']
      }
      this.humanAnswer = "";
      this.isDisabled = false;
      this.isCorrect = true;
      this.numberQuestion += 1;
      this.viewNumberQuestion > 59 ? this.viewNumberQuestion = 1 : this.viewNumberQuestion += 1;
      if (this.numberQuestion > this.questions.length) {
        this.$emit('updateResult', this.results)
        await this.postResults();
        await router.push('/result')
        return null
      }
      this.setQuestion(this.questions[this.numberQuestion - 1])
    },
    async postResults() {
      this.isLoad = true
      try {
        await axios.post(
          `${process.env.VUE_APP_SERVER}`,
          {
            result: this.results
          }
        );
      } catch (err) {
        alert("Error")
      } finally {
        this.isLoad = false;
      }
    }
  },
  created() {
    this.initQuestions();
    this.setQuestion(this.questions[0]);

  },
  watch: {
    humanAnswer(value) {
      if (value.length === 0) {
        return null
      }
      this.isDisabled = true;
      if (value !== this.question['correct_answer']) {
        this.isCorrect = false
      }
    }
  }
}

</script>

<template>
  <div class="test">
    <div class="header">
      <div class="container">
        <div class="question">
          <div class="question__block">
            <img src="@/assets/circle.svg" alt="">
            <span>{{ this.question['block'] }} Блок</span>
          </div>
          <div class="row mt-lg-4">
            <div class="question__theme offset-1 col-lg-8 col-7">
              {{ this.question['theme'] }}
            </div>
            <div class="question__number offset-1 col-lg-2 col-3">
              <span>Вопрос {{ this.viewNumberQuestion }}/60</span>
            </div>
          </div>
          <div class="question__text offset-1 col-lg-8 col-10 mt-4">
            {{ this.question['text'] }}
          </div>
          <div class="question__animal">
            <img src="@/assets/лисица.png" alt="">
          </div>
        </div>
      </div>
    </div>
    <div class="answers">
      <div class="container">
        <div class="question__answers" v-for="(item, index) in this.question['answers']">
          <input type="radio" :id="`${index}`" :name="`answer-${this.numberQuestion}`" :value="`${item}`"
            v-model="this.humanAnswer" :disabled="isDisabled" />
          <label class="test__answer col-12" :for="`${index}`"
            :class="{ incorrect_answer: this.checkIncorrectAnswer(item), default_answer: this.checkDefaultAnswer(item), correct_answer: this.checkCorrectAnswer(item) }">{{
              item }}</label>
        </div>
        <div class="question__annotation offset-0 col-12 offset-lg-1 col-lg-10" v-if="!isCorrect">
          {{ this.question['annotation'] }}
        </div>
        <div v-if="this.isDisabled">
          <button class="question__btn offset-lg-10 col-lg-2 offset-7 col-5 mt-5" @click="nextQuestion">{{
            this.numberQuestion === this.questions.length ? "Завершить" : "Далее" }}</button>
        </div>
      </div>
    </div>
    <Loader v-if="this.isLoad" />
  </div>
</template>

<style scoped>
.header {
  padding-top: 50px;
  border-radius: 0 0 30px 30px;
  background: var(--Linear, linear-gradient(89deg, #BEF440 1.57%, #6DEF9E 99.46%));
}

.question {
  padding-top: 56px;
  padding-bottom: 56px;
  position: relative;
  border-radius: 30px;
  background: #FFF;
  box-shadow: 0 4px 19px 0 rgba(158, 192, 157, 0.25);
  transform: translateY(20%);
  min-height: 350px;
}

.question__block {
  position: absolute;
  transform: translateY(-50%);
  text-align: center;
  margin-left: auto;
  margin-right: auto;
  left: 0;
  right: 0;
  top: 0;
  width: 160px;
  height: 160px;
}

.question__block img {
  display: block;
  min-width: 100%;
  margin: 0 auto;
}

.question__block span {
  position: absolute;
  top: 50%;
  left: 0;
  width: 100%;
  margin-top: -10px;
  color: #283128;
  text-align: center;
  text-shadow: 0 4px 73px rgba(134, 169, 133, 0.75);
  font-size: 20px;
  font-weight: 600;
  line-height: 20px;
  text-transform: uppercase;
}

.question__theme {
  font-size: 20px;
  font-weight: 400;
  color: #283128;
}

.question__number {
  font-size: 20px;
  color: #283128;
}

.question__text {
  color: #000;
  font-size: 27px;
  line-height: 30px;
  font-weight: 600;
}

.question__animal {
  z-index: -1;
  position: absolute;
  bottom: 0;
  right: 0;
}

.question__animal img {
  width: 300px;
}

.answers {
  padding-top: 70px;
  margin-top: 50px;
  padding-bottom: 50px;
}

.question__answers input[type=radio] {
  display: none;
}

.test__answer {
  cursor: pointer;
  padding: 16px 90px;
  font-size: 20px;
  line-height: 30px;
  user-select: none;
  text-align: center;
  border-radius: 25px;
  border: 4px solid rgba(158, 192, 157, 0.35);
  background: #FFF;
  margin-top: 16px;
}

/* Hover */
.question__answers label:hover {
  color: #666;
}

.correct_answer {
  border: 3px solid var(--Linear, #BEF440);
}

.incorrect_answer {
  border: 4px solid #FF6770;
}

.default_answer {
  border: 4px solid rgba(158, 192, 157, 0.35);
}

.question__annotation {
  margin-top: 90px;
  font-size: 27px;
  font-weight: 500;
  line-height: 33px;
}

.question__btn {
  padding: 12px 0;
  border-radius: 15px;
  border: 4px solid rgba(158, 192, 157, 0.35);
  background: #FFF;
  color: black;

  font-size: 20px;
  font-weight: 500;
  line-height: 30px;
}

@media (max-width: 1200px) {
  .question__animal img {
    width: 250px;
  }
}

@media (max-width: 992px) {
  .header {
    padding-top: 10px;
  }

  .question__animal img {
    width: 150px;
  }

  .question {
    padding-bottom: 120px;
  }

  .question__block {
    width: 90px;
    height: 90px;
  }

  .question__block img {
    width: 100%;
  }

  .question__block span {
    margin-top: -6px;
    font-size: 12px;
    line-height: 12px;
  }

  .question__theme {
    font-size: 13px;
    line-height: 13px;
  }

  .question__number {
    font-size: 12px;
  }

  .question__text {
    font-size: 18px;
    line-height: 20px;
    font-weight: 500;
  }

  .test__answer {
    padding: 20px 90px;
    font-size: 16px;
    line-height: 16px;
  }

  .question__annotation {
    margin-top: 36px;
    font-size: 16px;
    line-height: 18px;
  }

  .question__btn {
    padding: 12px 0;

    font-size: 14px;
    font-weight: 400;
    line-height: 18px;
  }
}
</style>