<template>
    <div class="card mb-4">
        <div class="pb-0 card-header mb-0">
            <h6 style="font-weight: bold; font-size: large;">상반기 위험 행동 총합</h6>
        </div>
        <div class="p-3 card-body">
            <div class="chart">
                <canvas id="thin-bar-chart" class="chart-canvas" height="300"></canvas>
            </div>
        </div>
    </div>
</template>

<script>
import Chart from 'chart.js/auto';

export default {
    name: "ThinBarChart",
    props: {
        title: {
        type: String,
        },
    },
    mounted() {
        this.renderChart();
    },
    methods: {
        renderChart() {
            const ctx2 = document.getElementById("thin-bar-chart").getContext("2d");
            new Chart(ctx2, {
                type: "bar",
                data: {
                    labels: ['1월', '2월', '3월', '4월', '5월', '6월'],
                    datasets: [{
                        label: '총 횟수',
                        data: [14, 6, 16, 14, 14, 22],
                        backgroundColor: ['#722FBA', '#2F46BA', '#722FBA', '#722FBA', '#722FBA', '#BD0027'],
                        borderRadius: Number.MAX_VALUE,
                        borderSkipped: false,
                        barThickness: 18,
                    }]
                },
                options: {
                    responsive: true,
                    maintainAspectRatio: false,
                    plugins: {
                        legend: {
                            display: false,
                        },
                    },
                    scales: {
                        y: {
                            grid: {
                                drawBorder: false,
                                display: false,
                                drawOnChartArea: false,
                                drawTicks: false,
                                borderDash: [5, 5],
                            },
                            ticks: {
                                display: true,
                                padding: 10,
                                color: "#343a40",
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
                                display: true,
                                drawOnChartArea: true,
                                drawTicks: false,
                                borderDash: [5, 5],
                            },
                            ticks: {
                                display: true,
                                padding: 10,
                                color: "#343a40",
                                font: {
                                size: 13,
                                family: "Open Sans",
                                style: "normal",
                                lineHeight: 2,
                                }
                            }
                        }
                    },
                },
            });
        }
    }
};
</script>