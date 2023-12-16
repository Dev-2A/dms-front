<template>
    <default-line-chart 
        :chart="Chart"
    />
</template>

<script>
import DefaultLineChart from "@/examples/Charts/DefaultLineChart.vue";

export default {
    name: "DMS-line-chart",
    data() {
        return {
            Chart: {
                type: "line",
                data: {
                    labels: ['1월', '2월', '3월', '4월', '5월', '6월',
        '7월', '8월', '9월', '10월', '11월', '12월'],
                    datasets: [
                                {
                                    label: '졸음',
                                    data: [0, 0, 0, 1, 3, 2,
                                0, 0, 3, 0, 3, 1],
                                    tension: 0.4,
                                    borderWidth: 0,
                                    pointRadius: 0,
                                    borderColor: "#2F46BA"
                                },
                                {
                                    label: '통화',
                                    data: [6, 3, 5, 4, 4, 6,
                                4, 2, 15, 4, 18, 15]
                                },
                                {
                                    label: '문자',
                                    data: [8, 3, 11, 9, 7, 14,
                                    3, 17, 13, 6, 12, 19]
                                }
                            ]
                },
                options: {
                    responsive: true,
                    maintainAspectRatio: false,
                    plugins: {
                        legend: {
                            display: false,
                        },
                    },
                    interaction: {
                        intersect: false,
                        mode: "index",
                    },
                    scales: {
                        y: {
                            grid: {
                                drawBorder: false,
                                display: true,
                                drawOnChartArea: true,
                                drawTicks: false,
                                borderDash: [5, 5],
                            },
                            ticks: {
                                display: true,
                                padding: 10,
                                color: "#fbfbfb",
                                font: {
                                    size: 13,
                                    family: "Open Sans",
                                    style: "normal",
                                    lineHeight: 2,
                                },
                            },
                        },
                        x: {
                            grid: {
                                drawBorder: false,
                                display: false,
                                drawOnChartArea: false,
                                drawTicks: false,
                                borderDash: [5, 5],
                            },
                            ticks: {
                                display: true,
                                color: "#ccc",
                                padding: 20,
                                font: {
                                    size: 13,
                                    family: "Open Sans",
                                    style: "normal",
                                    lineHeight: 2,
                                },
                            },
                        },
                    },
                },
            },
        };
    },
    components: {
        DefaultLineChart,
    },
};
</script>