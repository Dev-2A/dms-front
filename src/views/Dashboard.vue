<template>
  <div class="py-4 container-fluid">
    <div class="row">
      <div class="col-lg-12">
        <div class="row">
          <div class="col-lg-3 col-md-6 col-12">
            <card
              style="
                background-color: orange;
              "
              :title="stats.drowsy.title"
              :value="stats.drowsy.value"
              :percentage="stats.drowsy.percentage"
              :iconClass="stats.drowsy.iconClass"
              :iconBackground="stats.drowsy.iconBackground"
              :detail="stats.drowsy.detail"
              directionReverse
            ></card>
          </div>
          <div class="col-lg-3 col-md-6 col-12">
            <card
              :title="stats.Calling.title"
              :value="stats.Calling.value"
              :percentage="stats.Calling.percentage"
              :iconClass="stats.Calling.iconClass"
              :iconBackground="stats.Calling.iconBackground"
              :detail="stats.Calling.detail"
              directionReverse
            ></card>
          </div>
          <div class="col-lg-3 col-md-6 col-12">
            <card
              :title="stats.clients.title"
              :value="stats.clients.value"
              :percentage="stats.clients.percentage"
              :iconClass="stats.clients.iconClass"
              :iconBackground="stats.clients.iconBackground"
              :percentageColor="stats.clients.percentageColor"
              :detail="stats.clients.detail"
              directionReverse
            ></card>
          </div>
          <div class="col-lg-3 col-md-6 col-12">
            <card
              :title="stats.sales.title"
              :value="stats.sales.value"
              :percentage="stats.sales.percentage"
              :iconClass="stats.sales.iconClass"
              :iconBackground="stats.sales.iconBackground"
              :detail="stats.sales.detail"
              directionReverse
            ></card>
          </div>
        </div>
        <div class="row">
          <div class="col-lg-7 mb-lg">
            <!-- line chart -->
            <div class="card z-index-2">
              <gradient-line-chart />
            </div>
          </div>
          <div class="col-lg-5">
            <carousel />
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
import GradientLineChart from "@/examples/Charts/GradientLineChart.vue";
import Carousel from "./components/Carousel.vue";
import CategoriesCard from "./components/CategoriesCard.vue";
import AuthorsTable from "./components/AuthorsTable.vue";

export default {
  name: "dashboard-default",
  data() {
    return {
      stats: {
        drowsy: {
          title: "Drowsy Count",
          value: "2",
          iconClass: "mdi mdi-sleep",
          iconBackground: "bg-gradient-warning",
        },
        Calling: {
          title: "Phon Calling Count",
          value: "8",
          iconClass: "mdi mdi-cellphone",
          iconBackground: "bg-gradient-success",
          detail: "Total Count 19",
        },
        clients: {
          title: "New Clients",
          value: "+3,462",
          percentage: "-2%",
          iconClass: "ni ni-paper-diploma",
          percentageColor: "text-danger",
          iconBackground: "bg-gradient-warning",
          detail: "since last quarter",
        },
        sales: {
          title: "Sales",
          value: "$103,430",
          percentage: "+5%",
          iconClass: "ni ni-cart",
          iconBackground: "bg-gradient-warning",
          detail: "than last month",
        },
      },
    };
  },
  components: {
    Card,
    GradientLineChart,
    Carousel,
    CategoriesCard,
    AuthorsTable
},
};
</script>