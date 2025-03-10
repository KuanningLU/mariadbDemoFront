<template>
  <div class="container">
    <div class="table-wrapper">
      <el-table :data="reservations" border class="table">
        <el-table-column prop="reservation_id" label="預約編號" />
        <el-table-column prop="student_id" label="學生編號" />
        <el-table-column prop="seat_id" label="座位編號" />
        <el-table-column prop="timeslot_id" label="時段編號" />
        <el-table-column prop="create_time" label="創建時間" />
      </el-table>
    </div>
  </div>
</template>

<script setup lang="ts">
import { onMounted, ref } from 'vue';
import type { Reservation } from './interfaces/Reservations';
import { asyncGet } from './utils/fetch';
import { apis } from './enum/api';
const reservations = ref<Array<Reservation>>([])

onMounted(() => {
  asyncGet(apis.test).then((resp: Array<Reservation>) => {
    reservations.value = resp
  })
})
</script>

<style scoped lang="scss">
.container {
  width: 100%;
  height: 100vh;
  display: flex;
  align-items: center;
  justify-content: center;
  background-color: #f8f9fa;
  padding: 20px;
}

.table-wrapper {
  width: 80%;
  max-width: 1000px;
  background: white;
  border-radius: 10px;
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
  padding: 15px;
  overflow: hidden;
}

.table {
  width: 100%;
}

:deep(th) {
  background-color:rgb(178, 201, 228) !important;
  color: white !important;
  font-weight: bold !important;
  text-align: center !important;
  white-space: nowrap !important; /* 確保標題不換行 */
  padding: 12px !important;
}

:deep(td) {
  text-align: center !important;
  font-size: 14px !important;
}

:deep(.el-table__row:hover) {
  background-color: #e9f5ff !important;
}

:deep(.el-table__cell) {
  border-bottom: 1px solid #ddd !important;
}
</style>