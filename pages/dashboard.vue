<script setup lang="ts">
import { useTheme } from "vuetify";

const vuetifyTheme = useTheme();

const currentTheme = computed(() => vuetifyTheme.current.value.colors);

const series = ref([
  {
    name: "จำนวนหน่วย",
    type: "column",
    data: [168, 230, 510, 525, 461, 765],
  },
  {
    name: "ค่าไฟฟ้า",
    type: "line",
    data: [168, 230, 510, 525, 461, 765],
  },
]);

const chartOptions = ref({
  chart: {
    type: "line",
  },
  colors: ["#16B1FF", "#FF4C51"],
  xaxis: {
    categories: ["พ.ย.", "ธ.ค.", "ม.ค.", "ก.พ.", "มี.ค.", "เม.ย."],
  },
  yaxis: [
    {
      title: {
        text: "จำนวนหน่วย",
      },
    },
    {
      opposite: true,
      title: {
        text: "ค่าไฟฟ้า",
      },
    },
  ],
  title: {
    text: "ประวัติการใช้ไฟฟ้า",
  },
});
</script>

<template>
  <v-row class="match-height">
    <v-col cols="6" v-for="i in 4" :key="i">
      <VCard :to="`/room/lab ${i}`">
        <VCardText>
          <div class="d-flex justify-space-between">
            <h4 class="text-h4 mb-5 text-primary">LAB {{ i }}</h4>
            <v-btn> ดูเพิ่มเติม </v-btn>
          </div>

          <VueApexCharts
            :options="chartOptions"
            :series="series"
            class="my-1"
          />
        </VCardText>
      </VCard>
    </v-col>
  </v-row>
</template>

<style lang="scss" scoped></style>
