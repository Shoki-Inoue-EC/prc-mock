<template>
  <v-card>
    <v-card-title>Bar Chart</v-card-title>
    <v-card-text>
      <canvas ref="canvas"></canvas>
    </v-card-text>
  </v-card>
</template>

<script setup>
import { onMounted, ref } from 'vue'
import { Chart, registerables } from 'chart.js'

Chart.register(...registerables)

const canvas = ref(null)

onMounted(() => {
  new Chart(canvas.value, {
    type: 'bar',
    data: {
      labels: ['Jan', 'Feb', 'Mar', 'Apr'],
      datasets: [{
        label: 'Sales',
        data: [12, 19, 3, 5],
        backgroundColor: '#1976D2'
      }]
    },
    options: {
      responsive: true
    }
  })
})
</script>