<template>
  <div class="pb-3">
    <filter-label label="Qty"></filter-label>
    <div class="pb-3 md:flex sm:w-2/3">
      <div class="flex qty w-full m-3 ml-0 border-2 rounded-full border-light md:ml-3">
        <button class="qtyCell"
                @click="decreaseCounter">-
        </button>
        <div class="qtyCell">
          {{ count }}
        </div>
        <button class="qtyCell"
                @click="increaseCounter">+
        </button>
      </div>
      <button class="inline flex text-xl justify-center items-center w-full py-3 px-5 m-3 ml-0 text-white rounded-full md:ml-3 bg-primary"
              @click="alertCard(count)"> Submit</button>
    </div>
  </div>
</template>

<script>
import FilterLabel from "./FilterLabel.vue";
export default {
  components: {FilterLabel},
  props: ['alertCard'],
  data: () => ({
    count: 1
  }),
  methods: {
    increaseCounter() {
      this.count++
    },
    decreaseCounter() {
      if(this.count === 0) {
        return
      } else {
        this.count--
      }
    },
  }
}
</script>

<style scoped>
.bg-primary{
  background-color: #193c64;
}
.qtyCell {
  --tw-border-opacity: 1;
  border-right: 2px;
  border-color: rgba(223,223,223,var(--tw-border-opacity));
  border-style: solid;
  display: flex;
  justify-content: center;
  padding-bottom: 0.75rem;
  padding-top: 0.75rem;
  width: 33.333333%;
}
.qtyCell:last-child {
  border-right-width: 0;
  cursor: pointer;
}
.qtyCell:first-child {
  cursor: pointer;
}
</style>