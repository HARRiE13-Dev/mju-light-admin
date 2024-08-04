<script setup lang="ts">
const desserts = [
  {
    name: "Lab 1",
    count: "4/8",
    price: "862.-",
    temp: "26.5 C",
  },
  {
    name: "Lab 2",
    count: "4/8",
    price: "862.-",
    temp: "26.5 C",
  },
  {
    name: "Lab 3",
    count: "4/8",
    price: "862.-",
    temp: "26.5 C",
  },
  {
    name: "Lab 4",
    count: "4/8",
    price: "862.-",
    temp: "26.5 C",
  },
];
</script>

<template>
  <div class="d-flex justify-space-between mb-5">
    <h2>ตารางข้อมูลห้องเรียน</h2>
    <v-btn variant="outlined" color="primary"> เพิ่มห้องเรียน </v-btn>
  </div>
  <v-card>
    <v-table>
      <thead>
        <tr>
          <th class="text-left">ชื่อห้อง</th>
          <th class="text-left">หลอดไฟ (จำนวน)</th>
          <th class="text-left">ค่าไฟฟ้า (เปิด/ปิด)</th>
          <th class="text-left">อุณหภูมิ</th>
          <th class="text-left">จัดการ</th>
        </tr>
      </thead>
      <tbody>
        <tr v-for="item in desserts" :key="item.name">
          <td>{{ item.name }}</td>
          <td>{{ item.count }}</td>
          <td>{{ item.price }}</td>
          <td>{{ item.temp }}</td>
          <td class="d-flex ga-2 pa-2">
            <v-btn color="warning" flat> edit </v-btn>
            <v-btn color="success" flat> delete </v-btn>
          </td>
        </tr>
      </tbody>
    </v-table>
  </v-card>
</template>

<style lang="sass" scoped></style>
