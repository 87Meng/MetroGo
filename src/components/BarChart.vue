<template>
  <Bar
    id="my-chart-id"
    aria-label="GOOD"
    :options="chartOptions"
    :data="chartData"
  />
</template>

<script>
import { Bar } from "vue-chartjs";
import {
  Chart as ChartJS,
  Title,
  Tooltip,
  Legend,
  BarElement,
  CategoryScale,
  LinearScale,
} from "chart.js";

ChartJS.register(
  Title,
  Tooltip,
  Legend,
  BarElement,
  CategoryScale,
  LinearScale
);

export default {
  name: "BarChart",
  components: { Bar },
  props: {
    chartData: { type: Object, required: true },
    chartOptions: {
      type: Object,
      default: () => ({ responsive: true }),
      animation: {
        duration: 1000,
        easing: "easeOutQuart",
      },
    },
  },
};
</script>
