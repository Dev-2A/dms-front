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
              :iconClass="stats.drowsy.iconClass"
              :percentageColor="stats.drowsy.percentageColor"
              :iconBackground="stats.drowsy.iconBackground"
              :detail="stats.drowsy.detail"
              directionReverse
            ></card>
          </div>
          <div class="col-lg-3 col-md-6 col-12">
            <card style="background-color: #F5F1D6;"
              :title="stats.Calling.title"
              :total="stats.Calling.total"
              :value="stats.Calling.value"
              :percentage="stats.Calling.percentage"
              :iconClass="stats.Calling.iconClass"
              :percentageColor="stats.Calling.percentageColor"
              :iconBackground="stats.Calling.iconBackground"
              :detail="stats.Calling.detail"
              directionReverse
            ></card>
          </div>
          <div class="col-lg-3 col-md-6 col-12">
            <card style="background-color: #F5F1D6;"
              :title="stats.Texting.title"
              :total="stats.Texting.total"
              :value="stats.Texting.value"
              :percentage="stats.Texting.percentage"
              :iconClass="stats.Texting.iconClass"
              :iconBackground="stats.Texting.iconBackground"
              :percentageColor="stats.Texting.percentageColor"
              :detail="stats.Texting.detail"
              directionReverse
            ></card>
          </div>
          <div class="col-lg-3 col-md-6 col-12">
            <card style="background-color: #F5F1D6;"
              :title="stats.Smoking.title"
              :total="stats.Smoking.total"
              :value="stats.Smoking.value"
              :percentage="stats.Smoking.percentage"
              :iconClass="stats.Smoking.iconClass"
              :iconBackground="stats.Smoking.iconBackground"
              :detail="stats.Smoking.detail"
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
          <div class="col-lg-3 col-md-6 col-12">
            <DefaultLineChart />
          </div>
        </div>
        <div class="row mt-4">
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
        </div>
      </div>
    </div>
  </div>
</template>
<script>
import Card from "@/examples/Cards/Card.vue";
import AuthorsTable from "@/views/components/AuthorsTable.vue";
import CategoriesCard from "@/views/components/CategoriesCard.vue";
import GradientLineChart from "@/examples/Charts/GradientLineChart.vue";
import VideoCard from "@/examples/Cards/VideoCard.vue";
import DefaultLineChart from "@/examples/Charts/DefaultLineChart.vue";

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
          iconClass: "mdi mdi-sleep",
          percentageColor: "text-danger",
          iconBackground: "bg-gradient-warning",
          detail: "지난 달보다",
        },
        Calling: {
          title: "통화",
          total: "누적",
          value: "57",
          percentage: "3회 감소",
          iconClass: "mdi mdi-cellphone",
          percentageColor: "text-info",
          iconBackground: "bg-gradient-success",
          detail: "지난 달보다",
        },
        Texting: {
          title: "문자 메시지",
          total: "누적",
          value: "123",
          percentage: "7회 증가",
          iconClass: "mdi mdi-message",
          percentageColor: "text-danger",
          iconBackground: "bg-gradient-warning",
          detail: "지난 달보다",
        },
        Smoking: {
          title: "흡연",
          total: "누적",
          value: "0",
          percentage: "0회",
          iconClass: "mdi mdi-smoking",
          iconBackground: "bg-gray-500",
          detail: "지난 달보다",
        },
      },
    };
  },
  components: {
    Card,
    AuthorsTable,
    CategoriesCard,
    GradientLineChart,
    DefaultLineChart,
    VideoCard
},
};
</script>