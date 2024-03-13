<template>
<Doughnut :data="chartData" :options="chartOptions"></Doughnut>
</template>

<script>
import { Chart as ChartJS, ArcElement, Tooltip, Legend } from 'chart.js';
import { Doughnut } from 'vue-chartjs';

ChartJS.register(ArcElement, Tooltip, Legend)

export default {
    data: () => ({
        chartData:{
            labels:['Avianca', 'KLM', 'Emirates', 'LATAM'],
            datasets:[{
                backgroundColor:['#f20300', '#009cdd', '#dda62b', '#1a0185'],
                data:[100,50,70,40]
            }]
        },
        chartOptions:{
            responsive: true
        }
    }),
    components: {
        Doughnut
    }
}
</script>

<style></style>