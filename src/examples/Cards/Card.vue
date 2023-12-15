<template>
  <div class="mb-4 card">
    <div class="p-3 card-body">
      <div class="d-flex" :class="directionReverse ? reverseDirection : ''">
        <div>
          <div class="text-center icon icon-shape"
            :class="`${iconBackground} ${this.$store.state.isRTL ? 'border-radius-md' : 'border-radius-2xl'}`">
            <i class="text-3xl" :class="iconClass" aria-hidden="true"></i>
          </div>
        </div>
        <div :class="contentClass">
          <div class="numbers" v-if="this.$store.state.isRTL">
            <p class="mb-0 text-uppercase text-bolder text-black" :class="titleColor">{{ title }}</p>
            <div class="container">
              <p :class="total" class="mb-0 text-black font-weight-light text-sm">{{ total }}</p>
              <h5 class="font-weight-bolder" :class="valueColor">{{ value }}</h5>
            </div>
            <span class="text-sm"  :class="percentageColor">{{ percentage }}</span>
            <span class="font-weight-light text-sm">{{detail}}</span>
          </div>
          <div class="numbers" v-else>
            <p class="mb-0 text-sm text-uppercase font-weight-bold" :class="titleColor">{{ title }}</p>
            <div class="container">
              <p :class="total" class="mb-0 text-black font-weight-light text-sm">{{ total }}</p>
              <h5 class="font-weight-bolder" :class="valueColor">{{ value }}</h5>
            </div>
            <span class="text-sm"  :class="percentageColor">{{ percentage }}</span> 
            {{detail}}
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "card",
  data() {
    return {
      reverseDirection: "flex-row-reverse justify-content-between",
    };
  },
  props: {
    directionReverse: Boolean,
    title: {
      type: String,
      required: true,
    },
    total: {
      type: String,
    },
    detail: {
      type: String,
      required: true,
    },
    titleColor: {
      type: String,
    },
    value: {
      required: true,
    },
    valueColor: {
      type: String,
    },
    percentage: String,
    iconClass: {
      type: String,
      required: true,
    },
    percentageColor: {
      type: String,
      default: "text-info",
    },
    iconBackground: {
      type: String,
      default: "bg-white",
    },
    contentClass: {
      type: String,
    },
  },
};
</script>

<style>
.container {
  display: flex;
}

.container p {
  margin-top: 2px;
  margin-right: 3px;
}

.container h5 {
  margin-top: 0;
  margin-left: 1px;
}
</style>