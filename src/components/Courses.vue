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
        <tr v-for="course in coursesData" :key="course.id">
          <td> {{course.id}}</td>
          <td> {{course.name}}</td>
          <td> {{course.semester}}</td>
          <td> {{course.grade}}</td>
        </tr>	
      </tbody>
    </table>
    <br />
    <br />
    <Add @course="addCourse"/>
  </div>
</template>

<script>
import Add from "./Add";
export default {
  name: "Courses",
  components: {
    Add
  },
  data() {   
    return {
      coursesData: [
        {
          id: 1,
          name: "Agile software development",
          semester: 1,
          grade: 82
        },
        {
          id: 2,
          name: "System modeling",
          semester: 1,
          grade: 85
        },
        {
          id: 3,
          name: "Object-oriented programming",
          semester: 1,
          grade: 99
        },
        {
          id: 4,
          name: "Estonian language Level A2",
          semester: 2,
          grade: 65
        }
      ]
    }
  },
  mounted: function() {
    this.$nextTick(function () {
    this.calcGPA();
  })
  },
  methods: {
    addCourse: function(course) {
      course.id = this.coursesData.length + 1;
      this.coursesData.push(course);
      this.calcGPA();
    },
    calcGPA: function() {
      var sum = 0;
        var count = 0
        this.coursesData.forEach(e => {
            count +=1;
            var grade = e.grade;
            if (grade > 90) {
                sum +=4;
            }
            else if (grade > 80 && grade <=90) {
                sum +=3;
            }
            else if (grade > 70 && grade <=80) {
                sum +=2;
            }
            else if (grade > 60 && grade <=70) {
                sum +=1;
            }
            else if (grade > 50 && grade <=60) {
                sum +=0.5;
            }
        });
        this.$root.$emit('gpa', sum/count);
    }
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