<template>
  <div class="quiz-page">
    <div class="background-overlay"></div>
    <div class="hammer-sickle"></div>
    <div class="quiz-container">
      <div class="header">
        <div class="star"></div>
        <h2>Quiz: Revolución Rusa</h2>
        <div class="star"></div>
      </div>
      <p class="intro">Responde las preguntas y pon a prueba tus conocimientos sobre este importante evento histórico. ¡Buena suerte, camarada!</p>

      <div class="question-card" v-for="(question, index) in questions" :key="index">
        <div class="question-number">{{ index + 1 }}</div>
        <p>{{ question.text }}</p>
        <div class="options">
          <label v-for="(option, optIndex) in question.options" :key="optIndex" class="option-label">
            <input type="radio" :name="'question' + index" :value="option" v-model="selectedAnswers[index]" />
            <span class="custom-radio"></span>
            {{ option }}
          </label>
        </div>
      </div>

      <div class="button-container">
        <button @click="checkAnswers" :disabled="quizCompleted" class="submit-button">
          Enviar Respuestas
        </button>
        <button v-if="quizCompleted" @click="resetQuiz" class="reset-button">
          Reiniciar Quiz
        </button>
      </div>

      <div v-if="quizCompleted" class="result" :class="{ 'perfect-score': score === questions.length }">
        <h3>Tu Puntaje: {{ score }} / {{ questions.length }}</h3>
        <p v-if="score === questions.length">¡Excelente trabajo, camarada! Has demostrado un perfecto entendimiento de la Revolución.</p>
        <p v-else>Sigue estudiando la historia revolucionaria para mejorar tu puntuación.</p>
      </div>
    </div>
  </div>
</template>

<script setup>
import { ref } from 'vue';

const questions = [
  { text: "¿En qué año ocurrió la Revolución de Octubre?", options: ["1917", "1918", "1919", "1920"], correctAnswer: "1917" },
  { text: "¿Quién lideró la Revolución de Octubre?", options: ["Leon Trotsky", "Vladimir Lenin", "Joseph Stalin", "Nicolás II"], correctAnswer: "Vladimir Lenin" },
  { text: "¿Qué movimiento derrocó al Zar Nicolás II?", options: ["Revolución de Octubre", "Revolución de Febrero", "Revolución Industrial", "Revolución Francesa"], correctAnswer: "Revolución de Febrero" },
  { text: "¿Qué tratado sacó a Rusia de la Primera Guerra Mundial?", options: ["Tratado de Brest-Litovsk", "Tratado de Versalles", "Tratado de París", "Pacto de Varsovia"], correctAnswer: "Tratado de Brest-Litovsk" },
  { text: "¿Cuál era el nombre del último zar de Rusia?", options: ["Alejandro III", "Nicolás II", "Pedro el Grande", "Iván IV"], correctAnswer: "Nicolás II" },
  { text: "¿Qué partido lideró la Revolución de Octubre?", options: ["Mencheviques", "Bolcheviques", "Partido Comunista Chino", "Socialdemócratas"], correctAnswer: "Bolcheviques" },
  { text: "¿Qué año marcó el fin del Imperio Ruso?", options: ["1917", "1918", "1921", "1922"], correctAnswer: "1917" },
  { text: "¿Quién fue el estratega militar clave de los bolcheviques?", options: ["Leon Trotsky", "Joseph Stalin", "Vladimir Lenin", "Karl Marx"], correctAnswer: "Leon Trotsky" },
  { text: "¿Qué sistema político se implementó tras la Revolución de Octubre?", options: ["Democracia liberal", "Socialismo", "Capitalismo", "Feudalismo"], correctAnswer: "Socialismo" },
  { text: "¿Cómo se llamaba el gobierno provisional tras la Revolución de Febrero?", options: ["Duma Estatal", "Gobierno Provisional", "Soviets de Obreros", "Partido Obrero Socialdemócrata"], correctAnswer: "Gobierno Provisional" },
];

const selectedAnswers = ref(Array(questions.length).fill(null));
const score = ref(0);
const quizCompleted = ref(false);

const checkAnswers = () => {
  score.value = 0;
  selectedAnswers.value.forEach((answer, index) => {
    if (answer === questions[index].correctAnswer) {
      score.value++;
    }
  });
  quizCompleted.value = true;
};

const resetQuiz = () => {
  selectedAnswers.value = Array(questions.length).fill(null);
  score.value = 0;
  quizCompleted.value = false;
};
</script>

<style scoped>
.quiz-page {
  position: relative;
  min-height: 100vh;
  background: linear-gradient(135deg, #1a1a1a 0%, #8b0000 100%);
  color: #ffffff;
  padding: 40px 20px;
  overflow: hidden;
}

.background-overlay {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background-image: 
    url("data:image/svg+xml,%3Csvg width='60' height='60' viewBox='0 0 60 60' xmlns='http://www.w3.org/2000/svg'%3E%3Cpath d='M30 0l30 30-30 30L0 30z' fill='%23ffffff' fill-opacity='0.05'/%3E%3C/svg%3E"),
    radial-gradient(circle at 20% 30%, rgba(139, 0, 0, 0.4) 0%, transparent 50%),
    radial-gradient(circle at 80% 70%, rgba(139, 0, 0, 0.4) 0%, transparent 50%);
  animation: backgroundMovement 20s infinite alternate;
}

.hammer-sickle {
  position: fixed;
  top: 20px;
  right: 20px;
  width: 100px;
  height: 100px;
  background-image: url("data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' viewBox='0 0 100 100'%3E%3Cpath fill='%23ffcc00' d='M50,0C22.4,0,0,22.4,0,50s22.4,50,50,50s50-22.4,50-50S77.6,0,50,0z M76.4,66.5l-8.9,8.9L43.6,51.5v17.8h-12V31.7h12v17.8L67.5,25.6l8.9,8.9L52.5,58.4L76.4,66.5z'/%3E%3C/svg%3E");
  opacity: 0.2;
  pointer-events: none;
  margin-top: 90px
}

.quiz-container {
  position: relative;
  max-width: 800px;
  margin: 0 auto;
  padding: 30px;
  background: rgba(0, 0, 0, 0.8);
  border-radius: 15px;
  box-shadow: 0 0 30px rgba(139, 0, 0, 0.5);
  border: 1px solid rgba(255, 204, 0, 0.3);
  margin-top: 60px;
}

.header {
  display: flex;
  align-items: center;
  justify-content: center;
  margin-bottom: 30px;
}

.star {
  width: 30px;
  height: 30px;
  background-image: url("data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' viewBox='0 0 24 24'%3E%3Cpath fill='%23ffcc00' d='M12 0l2.5 9h9.5l-7.5 5.5 3 9.5-7.5-5.5-7.5 5.5 3-9.5-7.5-5.5h9.5z'/%3E%3C/svg%3E");
  margin: 0 20px;
}

h2 {
  color: #ffcc00;
  font-size: 36px;
  text-transform: uppercase;
  letter-spacing: 2px;
  margin: 0;
  text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.5);
}

.intro {
  color: #cccccc;
  font-size: 18px;
  margin-bottom: 30px;
  text-align: center;
}

.question-card {
  background: rgba(139, 0, 0, 0.3);
  padding: 20px;
  margin: 20px 0;
  border-radius: 10px;
  border: 1px solid rgba(255, 204, 0, 0.2);
  position: relative;
  transition: transform 0.3s ease;
}

.question-card:hover {
  transform: translateX(5px);
}

.question-number {
  position: absolute;
  top: -15px;
  left: -15px;
  width: 30px;
  height: 30px;
  background: #ffcc00;
  color: #8b0000;
  border-radius: 50%;
  display: flex;
  align-items: center;
  justify-content: center;
  font-weight: bold;
  font-size: 16px;
}

.options {
  margin-top: 15px;
}

.option-label {
  display: block;
  margin: 10px 0;
  padding: 10px 15px;
  background: rgba(255, 255, 255, 0.1);
  border-radius: 5px;
  cursor: pointer;
  transition: all 0.3s ease;
  position: relative;
  padding-left: 40px;
}

.option-label:hover {
  background: rgba(255, 204, 0, 0.2);
}

.custom-radio {
  position: absolute;
  left: 15px;
  top: 50%;
  transform: translateY(-50%);
  width: 16px;
  height: 16px;
  border: 2px solid #ffcc00;
  border-radius: 50%;
}

input[type="radio"] {
  display: none;
}

input[type="radio"]:checked + .custom-radio::after {
  content: '';
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  width: 8px;
  height: 8px;
  background: #ffcc00;
  border-radius: 50%;
}

.button-container {
  display: flex;
  justify-content: center;
  gap: 20px;
  margin-top: 30px;
}

.submit-button, .reset-button {
  padding: 12px 25px;
  font-size: 16px;
  border: none;
  border-radius: 5px;
  cursor: pointer;
  transition: all 0.3s ease;
  text-transform: uppercase;
  letter-spacing: 1px;
  font-weight: bold;
}

.submit-button {
  background: #8b0000;
  color: #ffffff;
  border: 2px solid #ffcc00;
}

.submit-button:hover:not(:disabled) {
  background: #a00000;
  transform: translateY(-2px);
}

.submit-button:disabled {
  background: #4a4a4a;
  border-color: #666666;
  cursor: not-allowed;
}

.reset-button {
  background: #333333;
  color: #ffcc00;
  border: 2px solid #ffcc00;
}

.reset-button:hover {
  background: #444444;
  transform: translateY(-2px);
}

.result {
  margin-top: 30px;
  padding: 20px;
  background: rgba(139, 0, 0, 0.3);
  border-radius: 10px;
  text-align: center;
  border: 1px solid rgba(255, 204, 0, 0.3);
}

.perfect-score {
  background: rgba(255, 204, 0, 0.2);
  animation: glow 2s infinite alternate;
}

@keyframes glow {
  from {
    box-shadow: 0 0 10px rgba(255, 204, 0, 0.5);
  }
  to {
    box-shadow: 0 0 20px rgba(255, 204, 0, 0.8);
  }
}

@keyframes backgroundMovement {
  0% {
    background-position: 0% 0%;
  }
  100% {
    background-position: 100% 100%;
  }
}

@media (max-width: 600px) {
  .quiz-container {
    padding: 20px;
  }

  h2 {
    font-size: 24px;
  }

  .button-container {
    flex-direction: column;
  }

  .submit-button, .reset-button {
    width: 100%;
  }
}
</style>
