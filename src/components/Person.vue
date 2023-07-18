<template>
  <card>
    <template v-slot:card-header>
      <h1>{{ name }}</h1>
    </template>
    <!-- <template v-slot:card-button>
      <button @click="showDescription(id)">ดูรายละเอียด</button> &nbsp;
      <button @click="deleteEmployee(id)">ลบข้อมูล</button>
    </template>
   <template v-slot:card-content>
    <transition name="fade">
      <div v-show="isVisible">
        <p>เงินเดือน: {{ salary }} บาท ตำแหน่ง : {{ department }}</p>
      </div>
    </transition>
   </template> -->
   <template v-slot:card-content>
        <p>เงินเดือน : {{ salary }} บาท , เพศ : {{gender}}</p>
        <p>ตำแหน่งงาน : {{ department }}</p>
        <p>ทักษะด้านภาษา : {{skill}}</p>
    </template>
  </card>
</template>

<script>
import Card from './Card.vue';
export default {
  name: "Person",
  components:{
    Card
  },
  data() {
    return {
      message: "ข้อมูลพนักงาน",
    };
  },
  // props ส่ง จาก แม่ ไป หา ลูก
  props: {
    id: {
      type: Number,
    },
    name: {
      type: String,
      // required ระบุต้องกำหนดด้วยถ้าไม่ระบุก็ได้ก็ไม่ต้องใส่
      required: true,
    },
    salary: {
      type: Number,
      required: true,
      // กำหนดค้าเริ่มต้น
      default: 10000,
    },
    department: {
      type: String,
      required: true,
    },
    gender: {
      type: String,
      required: true,
    },
    skill: {
      type: Array,
      required: true,
    },
    isVisible: {
      type: Boolean,
    },
  },
  methods: {
    showDescription(id) {
      this.$emit("show", id);
    },
    deleteEmployee(id) {
      this.$emit("delete", id);
    },
  },
};
</script>

<!-- scoped การกำหนดเฉพาะใน component นี้ -->
<style scoped>

button {
  font: inherit;
  cursor: pointer;
  border: 1px solid #ff0077;
  background: #ff0077;
  color: #fff;
  padding: 0.05rem 1rem;
  box-shadow: 1px 1px 2px rgba(0, 0, 0, 0.26);
}
.fade-enter-from{
    opacity: 0;
}
.fade-enter-active{
    transition: all 0.5s linear;
}
</style>