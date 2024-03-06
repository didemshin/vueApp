<template>
  <hr>
  <div class="container">
    <h2>Öğrenci Listesi</h2>
    <table class="table table-striped">
      <thead>
      <tr>
        <th>Öğrenci İsmi</th>
        <th>Öğrenci Soyismi</th>
        <th>Öğrenci Numarası</th>
        <th>Öğrenci Sınıfı</th>
      </tr>
      </thead>
      <tbody>
      <tr v-for="student in students">
        <td>{{student.name}}</td>
        <td>{{student.surname}}</td>
        <td>{{student.number}}</td>
        <td>{{student.class}}</td>
      </tr>
      </tbody>
    </table>
  </div>
</template>

<script>
export default {
  name: "StudentList",
  data(){
    return{

    }
  },
  props:{
    students: {
      type: Array,
      required: true
    }
  },
}
</script>

<style scoped>

</style>