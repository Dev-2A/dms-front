<template>
    <div class="card">
        <div class="pb-0 card-header mb-0">
            <h6>{{ title }}</h6>
            <p class="text-sm">
            </p>
        </div>
        <div class="p-3 card-body">
            <div class="chart">
                <canvas id="chart-line-dms" class="chart-canvas" height="300"></canvas>
            </div>
        </div>
    </div>
</template>

<script>
import Chart from "chart.js/auto";

export default {
    name: "line-chart",

    props: {
        title: {
            type: String,
            default: "월별 누적 그래프",
        },
    },

    mounted() {
        var ctx1 = document.getElementById("chart-line-dms").getContext("2d");
        new Chart(ctx1, {
            type: "line",
            data: {
                labels: ["1월", "2월", "3월","4월", "5월", "6월", "7월", "8월", "9월", "10월", "11월", "12월"],
                datasets: [
                    {label: "Mobile apps",
                    tension: 0.2,
                    borderWidth: 5,
                    pointRadius: 3,
                    borderColor: "#2F46BA",
                    data: [0, 0, 0, 1, 3, 2, 0, 0, 3, 0, 3, 1],
                    maxBarThickness: 4,
                },
                ],
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
                        ticks: { // Y축 글자 조절
                            display: true,
                            padding: 10,
                            color: "#BD0027",
                            font: {
                                size: 15,
                                family: "Open Sans",
                                // weight: "bold",
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
                            color: "#722FBA",
                            padding: 20,
                            font: {
                                size: 15,
                                family: "Open Sans",
                                style: "normal",
                                lineHeight: 2,
                            },
                        },
                    },
                },
            },
        });
    },
};
</script>