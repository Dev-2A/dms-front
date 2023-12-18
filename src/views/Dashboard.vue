<template>
  <div class="py-4 container-fluid">
    <div class="row">
      <div class="col-lg-12">
        <!-- Cards -->
        <div class="row">
          <div class="col-lg-3 col-md-6 col-12">
            <card style="background-color: #F5F1D6;"
              :title="stats.drowsy.title"
              :total="stats.drowsy.total"
              :value="stats.drowsy.value"
              :percentage="stats.drowsy.percentage"
              :percentageColor="stats.drowsy.percentageColor"
              :iconBackground="stats.drowsy.iconBackground"
              :detail="stats.drowsy.detail"
              :iconImage="stats.drowsy.iconImage"
              directionReverse
            >
          </card>
          </div>
          <div class="col-lg-3 col-md-6 col-12">
            <card style="background-color: #F5F1D6;"
              :title="stats.Calling.title"
              :total="stats.Calling.total"
              :value="stats.Calling.value"
              :percentage="stats.Calling.percentage"
              :percentageColor="stats.Calling.percentageColor"
              :iconBackground="stats.Calling.iconBackground"
              :detail="stats.Calling.detail"
              :iconImage="stats.Calling.iconImage"
              directionReverse
            ></card>
          </div>
          <div class="col-lg-3 col-md-6 col-12">
            <card style="background-color: #F5F1D6;"
              :title="stats.Texting.title"
              :total="stats.Texting.total"
              :value="stats.Texting.value"
              :percentage="stats.Texting.percentage"
              :iconBackground="stats.Texting.iconBackground"
              :percentageColor="stats.Texting.percentageColor"
              :detail="stats.Texting.detail"
              :iconImage="stats.Texting.iconImage"
              directionReverse
            ></card>
          </div>
          <div class="col-lg-3 col-md-6 col-12">
            <card style="background-color: #F5F1D6;"
              :title="stats.Smoking.title"
              :total="stats.Smoking.total"
              :value="stats.Smoking.value"
              :percentage="stats.Smoking.percentage"
              :iconBackground="stats.Smoking.iconBackground"
              :detail="stats.Smoking.detail"
              :iconImage="stats.Smoking.iconImage"
              directionReverse
            ></card>
          </div>
        </div>
        <!-- Video -->
        <div class="row">
          <div class="col-12">
            <video-card />
          </div>
        </div>
          <!-- Charts -->
        <div class="row">
          <div class="col-12">
            <GradientLineChart/>
          </div>
        </div>
        <div class="row">
          <div class="col-lg-8 col-12">
            <DefaultLineChart />
          </div>
          <div class="col-lg-4 col-12">
            <ThinBarChart/>
          </div>
        </div>
        <!-- <div class="row mt-4">
          <div class="col-lg-7 mb-lg-0 mb-4">
            <div class="card">
              <div class="table-responsive">
                <authors-table />
              </div>
            </div>
          </div>
          <div class="col-lg-5">
            <categories-card />
          </div>
        </div> -->
      </div>
    </div>
  </div>
</template>
<script>
import Card from "@/examples/Cards/Card.vue";
// import AuthorsTable from "@/views/components/AuthorsTable.vue";
// import CategoriesCard from "@/views/components/CategoriesCard.vue";
import GradientLineChart from "@/examples/Charts/GradientLineChart.vue";
import VideoCard from "@/examples/Cards/VideoCard.vue";
import DefaultLineChart from "@/examples/Charts/DefaultLineChart.vue";
import ThinBarChart from "@/examples/Charts/ThinBarChart.vue";

import sleep from "@/assets/png/sleep.png";
import cellphone from "@/assets/png/cellphone.png";
import message from "@/assets/png/message.png";
import smoking from "@/assets/png/smoking.png";

export default {
  name: "dashboard-default",
  data() {
    return {
      stats: {
        drowsy: {
          title: "졸음",
          total: "누적",
          value: "13",
          percentage: "1회 증가",
          percentageColor: "text-danger",
          iconBackground: "bg-gradient-warning",
          detail: "지난 달보다",
          iconImage: sleep,
        },
        Calling: {
          title: "통화",
          total: "누적",
          value: "57",
          percentage: "3회 감소",
          percentageColor: "text-info",
          iconBackground: "bg-gradient-success",
          detail: "지난 달보다",
          iconImage: cellphone,
        },
        Texting: {
          title: "문자 메시지",
          total: "누적",
          value: "123",
          percentage: "7회 증가",
          percentageColor: "text-danger",
          iconBackground: "bg-gradient-warning",
          detail: "지난 달보다",
          iconImage: message,
        },
        Smoking: {
          title: "흡연",
          total: "누적",
          value: "0",
          percentage: "0회",
          iconBackground: "bg-gray-500",
          detail: "지난 달보다",
          iconImage: smoking,
        },
      },
    };
  },
  components: {
    Card,
    // AuthorsTable,
    // CategoriesCard,
    GradientLineChart,
    DefaultLineChart,
    VideoCard,
    ThinBarChart
},
};
</script>