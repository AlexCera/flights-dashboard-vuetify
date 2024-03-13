<template>
    <Bar :data="chartData" :options="chartOptions"></Bar>
</template>

<script>
import {
    Chart as ChartJS,
    Title,
    Tooltip,
    Legend,
    BarElement,
    CategoryScale,
    LinearScale
} from 'chart.js'
import { Bar } from 'vue-chartjs';

ChartJS.register(CategoryScale, LinearScale, BarElement, Title, Tooltip, Legend)

export default {
    data: () => ({
        chartData: {
            labels: ['January', 'February', 'March'],
            datasets: [
            {
                    label: 'Avianca',
                    backgroundColor: '#f20300',
                    data: [40, 55, 69],
                },
                {
                    label: 'KML',
                    backgroundColor: '#009cdd',
                    data: [10, 10, 10],
                },
                {
                    label: 'Emirates',
                    backgroundColor: '#dda62b',
                    data: [5, 7, 8],
                },
                {
                    label: 'LATAM',
                    backgroundColor: '#1a0185',
                    data: [50, 60, 40],
                },
            ]

        },
        chartOptions: {
            responsive: true
        }
    }),
    components: {
        Bar
    }
}
</script>

<style></style>