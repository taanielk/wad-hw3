<template>
  <div ref="course-container" id="courses-container" class="tab">
    <h1 class="title">Courses</h1>
    <table id="courses">
      <thead>
        <tr>
          <th>#</th>
          <th>Course Title</th>
          <th>Semester</th>
          <th>Grade</th>
        </tr>
      </thead>
      <tbody>
        <tr>
          <td>1</td>
          <td>Agile software development</td>
          <td>1</td>
          <td>82</td>
        </tr>
        <tr>
          <td>2</td>
          <td>System modeling</td>
          <td>1</td>
          <td>85</td>
        </tr>
        <tr>
          <td>3</td>
          <td>Object-oriented programming</td>
          <td>2</td>
          <td>99</td>
        </tr>
        <tr>
          <td>4</td>
          <td>Estonian language Level A2</td>
          <td>2</td>
          <td>65</td>
        </tr>
      </tbody>
    </table>
    <br />
    <br />
    <Add />
  </div>
</template>

<script>
import Add from "./Add";
export default {
  name: "Courses",
  components: {
    Add
  }
};
</script>>

<style scoped>
table {
  width: 100%;
  border-collapse: collapse;
}

table th {
  padding: 8px 12px;
  text-align: left;
  border: 1px solid #cbcbcb;
  background-color: #03a9f4;
  color: #ffffff;
}

table td {
  padding: 8px 12px;
  border: 1px solid #cbcbcb;
}
</style>