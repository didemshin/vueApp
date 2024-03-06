<template>
  <div class="container mt-5 mb-5">
    <div class="row">
      <h2>Yeni Öğrenci Form</h2>
      <form>
        <div class="form-group">
          <label for="name">Öğrenci İsmi</label>
          <input type="text" class="form-control" id="name" v-model="students.name" required>
        </div>
        <div class="form-group">
          <label for="surname">Öğrenci Soyismi</label>
          <input type="text" class="form-control" id="surname" v-model="students.surname" required>
        </div>
        <div class="form-group">
          <label for="number">Öğrenci Numarası</label>
          <input type="number" class="form-control" id="number" v-model="students.number" required>
        </div>
        <div class="form-group">
          <label for="class">Öğrenci Sınıfı</label>
          <input type="number" class="form-control" id="class" v-model="students.class" required>
        </div>
        <button type="submit" class="btn-block btn-primary" @click="addNewStudent">Ekle</button>
      </form>
    </div>
  </div>
  <student-list v-bind:students="this.studentList" v-if="this.studentList.length>0"></student-list>
</template>

<script>
  import StudentList from './StudentList.vue'
  export default {
    components: { StudentList },
    data() {
      return {
        students:{
          name: "",
          surname: "",
          number: "",
          class: "",
        },
        studentList:[],
      }
    },
    methods:{
      addNewStudent() {
        this.studentList.push(this.students)
        console.log(this.students)
        this.students = {
          name: "",
          surname: "",
          number: "",
          class: "",
        }
      },
    },
  };
</script>

<style scoped>
  input, textarea, button{padding: 8px 15px;border-radius: 5px !important;margin: 5px 0px;box-sizing: border-box;border: 1px solid #ccc;font-size: 18px !important;font-weight: 300}
  input:focus, textarea:focus{-moz-box-shadow: none !important;-webkit-box-shadow: none !important;box-shadow: none !important;border: 1px solid #00BCD4;outline-width: 0;font-weight: 400}
  .btn-block{text-transform: uppercase;font-size: 15px !important;font-weight: 400;height: 43px;cursor: pointer}
  button:focus{-moz-box-shadow: none !important;-webkit-box-shadow: none !important;box-shadow: none !important;outline-width: 0}
</style>