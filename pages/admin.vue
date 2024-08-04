<script setup lang="ts">
const desserts = [
  {
    name: "นายวิภา แก้วเจริญ",
    count: "บุคคลสาขา",
    price: "wipax@example.com",
    temp: "064-1234567",
  },
  {
    name: "นายวิภา แก้วเจริญ",
    count: "บุคคลสาขา",
    price: "wipax@example.com",
    temp: "064-1234567",
  },
  {
    name: "นายวิภา แก้วเจริญ",
    count: "บุคคลสาขา",
    price: "wipax@example.com",
    temp: "064-1234567",
  },
  {
    name: "นายวิภา แก้วเจริญ",
    count: "บุคคลสาขา",
    price: "wipax@example.com",
    temp: "064-1234567",
  },
 
];
</script>

<template>
  <div class="d-flex justify-space-between mb-5">
    <h2>ตารางข้อมูลผู้ดูแลระบบ</h2>
    <v-btn variant="outlined" color="primary"> เพิ่มผู้ดูแลระบบ </v-btn>
  </div>
  <v-card>
    <v-table>
      <thead>
        <tr>
          <th class="text-left">ชื่อ-นามสกุล</th>
          <th class="text-left">ตำแหน่ง</th>
          <th class="text-left">อีเมล</th>
          <th class="text-left">เบอร์โทร</th>
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
