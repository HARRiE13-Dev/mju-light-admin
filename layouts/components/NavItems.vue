<script lang="ts" setup>
import VerticalNavSectionTitle from '@/@layouts/components/VerticalNavSectionTitle.vue'
import VerticalNavGroup from '@layouts/components/VerticalNavGroup.vue'
import VerticalNavLink from '@layouts/components/VerticalNavLink.vue'
</script>

<template>
  <VerticalNavGroup
    :item="{
      title: 'ภาพรวม',
      icon: 'ri-home-smile-line',
    }"
  >
    <VerticalNavLink
      :item="{
        title: 'การวิเคราะห์',
        to: '/dashboard',
      }"
    />

  </VerticalNavGroup>


  <VerticalNavSectionTitle
    :item="{
      heading: 'การจัดการห้องเรียน',
    }"
  />
 
  <VerticalNavLink
    :item="{
      title: 'ตารางห้องเรียน',
      icon: 'ri-calendar-todo-line',
      to: '/room-view',
    }"
  />

  <VerticalNavGroup
    :item="{
      title: 'ห้องเรียน',
      icon: 'ri-stack-line',
    }"
  >
    <VerticalNavLink
      :item="{
        title: 'Lab 1',
        to: '/room/lab1',
      }"
    />
    <VerticalNavLink
      :item="{
        title: 'Lab 2',
        to: '/room/lab2',
      }"
    />
    <VerticalNavLink
      :item="{
        title: 'Lab 3',
        to: '/room/lab3',
      }"
    />
    <VerticalNavLink
      :item="{
        title: 'Lab 4',
        to: '/room/lab4',
      }"
    />

  </VerticalNavGroup>

  
  <VerticalNavSectionTitle
    :item="{
      heading: 'การจัดการผู้ดูแลระบบ',
    }"
  />
 
  <VerticalNavLink
    :item="{
      title: 'ผู้ดูแลระบบ',
      icon: 'ri-user-add-line',
      to: '/admin',
    }"
  />

</template>
