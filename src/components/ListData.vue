<template>
  <!-- <h1>{{ message }}</h1>
        <Person name="แอ็ค" salary=30000 />
        <Person name="จูน" salary=20000 />
        <Person name="โอม" salary=25000 /> -->

  <!-- dynamic prop -->
  <ul>
    <!-- <Card>พนักงานคนที่ 1</Card>
    <Card>พนักงานคนที่ 2</Card>
    <Card>พนักงานคนที่ 3</Card> -->
    <Person
      v-for="(item,index) in employees"
      :key="index"
      :name="item.name"
      :salary="item.salary"
      :department="item.department"
      :gender="item.gender"
      :skill="item.skill"
      
      
    />
     <!-- 
      :isVisible="item.isVisible"
      @show="toggleVisible"
      @delete="removeEmployee" -->
  </ul>
</template>

<script>
import Person from "./Person.vue";
// import Card from "./Card.vue";
export default {
  name: "ListDAta",
  components: {
    Person,
    // Card

  },
  props:["employees"]

  // data() {
  //   return {
  //     employees: [
  //       {
  //         id: 1,
  //         name: "แอ็ค",
  //         salary: 40000,
  //         department: "โปรแกรมเมอร์",
  //         isVisible: false
  //       },
  //       {
  //         id: 2,
  //         name: "จูน",
  //         salary: 30000,
  //         department: "เทสเตอร์",
  //         isVisible: false
  //       },
  //       {
  //         id: 3,
  //         name: "โอม",
  //         salary: 20000,
  //         department: "การตลาด",
  //         isVisible: false
  //       },
  //       {
  //         id: 4,
  //         name: "แฟร์",
  //         salary: 15000,
  //         department: "ฝ่ายขาย",
  //         isVisible: false
  //       },
  //       // {name:900},
  //       { id: 5, name: "ก๊อต", department: "โปรแกรมเมอร์", isVisible: false },
  //       {
  //         id: 6,
  //         name: "ต้อม",
  //         salary: 18000,
  //         department: "โปรแกรมเมอร์",
  //         isVisible: false
  //       },
  //     ],
  //   };
  // },
  // methods:{
  //   toggleVisible(id){
  //     this.employees = this.employees.map((item)=>{
  //       if(item.id === id){
  //           return {...item,isVisible:!item.isVisible}
  //       }
  //       return item
  //     })
  //   },
  //   removeEmployee(id){
  //     this.employees = this.employees.filter(item=>{
  //       return item.id !== id
  //     })
  //   }
  // }
};
</script>

<style scoped>
ul {
  list-style: none;
  margin: 1rem 0;
  padding: 0;
}
</style>