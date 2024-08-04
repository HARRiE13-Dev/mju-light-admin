<script setup lang="ts">
const route = useRoute();

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

const model = ref(true);
</script>

<template>
  <div class="d-flex justify-space-between">
    <h1 class="text-uppercase mb-5">{{ route.params.id }}</h1>
    <!-- <v-btn> ดูเพิ่มเติม </v-btn> -->
  </div>
  <v-row class="match-height">
    <v-col cols="8">
      <VCard>
        <VCardText>
          <VueApexCharts
            :options="chartOptions"
            :series="series"
            class="my-1"
          />
        </VCardText>
      </VCard>
    </v-col>
    <v-col cols="4">
      <h2>ควบคุมสวิตช์ภายใน</h2>
      <v-divider class="mb-5"></v-divider>

      <!-- <div class="d-flex align-center ga-5 pa-5 border" v-for="i in 7" :key="i">
        <v-switch width="100px" v-model="model"></v-switch>

        <div v-if="model">เปิด</div>
        <div v-else>ปิด</div>

        <div>หลอดไฟดวงที่ {{ i }}</div>
      </div> -->

      <v-item-group selected-class="bg-primary" multiple>
        <v-container>
          <v-row dense>
            <v-col v-for="n in 6" :key="n" cols="6">
              <v-item v-slot="{ isSelected, selectedClass, toggle }">
                <v-card
                  class="d-flex flex-column align-center ga-5 pt-3"
                  height="200"
                  @click="toggle"
                  :color="isSelected ? 'warning' : undefined"
                >
                  <v-icon size="50" >
                    {{
                      isSelected
                        ? "ri-lightbulb-flash-fill"
                        : "ri-lightbulb-line"
                    }}</v-icon
                  >
                  <div class="text-h3">
                    {{ isSelected ? "เปิด" : "ปิด" }}
                  </div>
                  <p class="text-h5">หลอดไฟดวงที่ {{ n }}</p>
                </v-card>
              </v-item>
            </v-col>
          </v-row>
        </v-container>
      </v-item-group>
    </v-col>
  </v-row>
</template>

<style lang="scss" scoped></style>
