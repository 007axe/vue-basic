<template>
  <header>
    <h1>ระบบจัดการข้อมูลพนักงาน</h1>
  </header>
  <FormComponent @save="insertEmployee" />
  <section class="employee-content" v-if="employees.length>0">
    <h2>ข้อมูลพนักงาน</h2>
    
    <!-- <ListData :employees="employees"/> -->

    <ListData :employees="employees"/>
    
  </section>
</template>

<script>
import ListData from './components/ListData.vue';
import FormComponent from './components/FormComponent.vue';

export default {
  name:"App",
  components:{
    ListData,
    FormComponent
  },
  data(){
    return{
      employees:[]
      // employees:[
      //   {name:"แอ็ค",salary:40000},
      //   {name:"จูน",salary:30000},
      //   {name:"โอม",salary:20000},
      //   {name:"แฟร์",salary:15000},
      //   // {name:900},
      //   {name:"ก๊อต"},
      //   {name:"ต้อม",salary:18000}
      // ]
    }
  },
  methods:{
        insertEmployee(data){
            this.employees.push(data);
            console.log("complect")
        }
    }
}
</script>

<style>
  *{
    box-sizing: border-box;
  }
  body{
    margin: 0;
    background: #ffffff;
  }
  header{
    box-shadow: 0 2px 8px rgba(0, 0, 0, 0.26);
    margin: 3rem;
    padding: 1rem;
    border-radius: 10px;
    background-color: purple;
    color: #fff;
    text-align: center;
  }
  .employee-content{
    box-shadow: 0 2px 8px rgba(0, 0, 0, 0.26);
    margin: 3rem;
    padding: 1rem;
    border-radius: 10px;
    text-align: center;

  }
  .employee-content h2{
    font-size: 2rem;
    border-bottom: 4px solid #ccc;
    color: purple;
    margin: 0 0 1rem 0;
  }
</style>