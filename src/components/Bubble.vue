<template>
    <Bubble :data="chartData" :options="chartOptions"></Bubble>
</template>

<script>
import {
    Chart as ChartJS,
    Tooltip,
    Legend,
    PointElement,
    LinearScale
} from 'chart.js'
import { Bubble } from 'vue-chartjs';

ChartJS.register(LinearScale, PointElement, Tooltip, Legend)

export default {
    data: () => ({
        chartData: {
            label: "text",
            datasets: [
                {
                    label: 'Avianca',
                    backgroundColor: '#f20300',
                    data: [
                        { x: 36, y: 36, r: 7 }
                    ]
                },
                {
                    label: 'KLM',
                    backgroundColor: '#009cdd',
                    data: [
                        { x: 15, y: 20, r: 7 }
                    ]
                },
                {
                    label: 'Emirates',
                    backgroundColor: '#dda62b',
                    data: [
                        { x: 25, y: 40, r: 7 }
                    ]
                },
                {
                    label: 'LATAM',
                    backgroundColor: '#1a0185',
                    data: [
                        { x: 40, y: 12, r: 7 }
                    ]
                },
            ]
        },
        chartOptions: {
            responsive: true
        }
    }),
    components: {
        Bubble
    }
}
</script>

<style></style>