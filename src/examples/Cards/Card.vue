<template>
  <div class="mb-4 card">
    <div class="p-3 card-body">
      <div class="d-flex" :class="directionReverse ? reverseDirection : ''">
        <div>
          <div class="text-center icon icon-shape"
            :class="`${iconBackground} ${this.$store.state.isRTL ? 'border-radius-md' : 'border-radius-2xl'}`">
              <div class="icon-image pt-2 align-self-center">
                <img :src="`${iconImage}`" alt="icon Image" />
              </div>
          </div>
        </div>
        <div :class="contentClass">
          <div class="numbers" v-if="this.$store.state.isRTL">
            <p class="mb-2 text-uppercase text-bolder text-black" :class="titleColor">{{ title }}</p>
              <p :class="total" class="mb-0 text-black font-weight-light text-sm">{{ total }}</p>
              <h5 class="font-weight-bolder" :class="valueColor">{{ value }}</h5>
            <span class="text-sm"  :class="percentageColor">{{ percentage }}</span>
            <span class="font-weight-light text-sm">{{detail}}</span>
          </div>
          <div class="numbers" v-else>
            <p class="titles mb-0 text-uppercase text-2xl font-weight-bolder">{{ title }}</p>
            <div class="container p-0 mt-2">
              <p :class="total" class="mb-0 pt-1 text-sm totalcolor">{{ total }}</p>
              <h5 class="font-weight-bolder valuecolor">{{ value }}</h5>
            </div>
            <div class="container p-0">
              <p :class="detail" class="mb-0 pt-1 text-sm">{{detail}}</p>
              <span class="text-lg font-weight-bolder" :class="percentageColor">{{ percentage }}</span>
            </div>
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
    value: {
      required: true,
    },
    percentage: String,
    iconImage: String,
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
  text-align: end;
  font-weight: 600;
}

.container h5 {
  margin-top: 0;
  margin-left: 1px;
}

.numbers p {
  font-size: 1.125rem;
}

.titles {
  color: black;
  font-size: larger;
}

.totalcolor {
  color: #6c757d;
}

.valuecolor {
  color: black;
}

.icon-image img {
  width: 32px;
  height: 32px;
  align-self: center;
}

</style>