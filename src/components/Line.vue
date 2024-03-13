<template>
    <Line :data="chartData" :options="chartOptions"></Line>
</template>

<script>
import {
    Chart as ChartJS,
    CategoryScale,
    LinearScale,
    PointElement,
    LineElement,
    Title,
    Tooltip,
    Legend
} from 'chart.js'
import { Line } from 'vue-chartjs';

ChartJS.register(
    CategoryScale,
    LinearScale,
    PointElement,
    LineElement,
    Title,
    Tooltip,
    Legend
)

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
            ],
        },
        chartOptions: {
            responsive: true
        }
    }),
    components: {
        Line
    }
}
</script>

<style></style>