<template>
  <div class="loader-overlay">
    <div class="loader">
      <div class="spinner"></div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Loader',
};
</script>

<style scoped>
.loader-overlay {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background: rgba(255, 255, 255, 0.7); /* Полупрозрачный белый фон */
  display: flex;
  justify-content: center;
  align-items: center;
  z-index: 9999; /* Выше всех остальных элементов */
}

.loader {
  width: 100px; /* Задайте размер вашего окружности */
  height: 100px;
  border-top: 8px solid #6DEF9E;
  border-right: 8px solid #6DEF9E;
  border-bottom: 8px solid #BEF440;
  border-left: 8px solid #BEF440;
//border-image: linear-gradient(95deg, #5A2BE1 24.85%, #B537F2 118%);
  border-radius: 50%;
  animation: spin 0.25s linear infinite;
}

.spinner {
  width: 0;
  height: 0;
}

@keyframes spin {
  0% {
    transform: rotate(0deg);
  }
  100% {
    transform: rotate(360deg);
  }
}
</style>
