<template>
  <div>
    <button @click="showAdd" id="add-course-button" class="blue-button">+</button>
    <span id="add-course" v-show="addVis">
      <input class="input" type="text" placeholder="Course title" ref="title" />
      <input class="input" type="number" min="1" max="8" placeholder="Semester" ref="semester" />
      <input class="input" type="number" min="0" max="100" placeholder="Grade" ref="grade" />
      <button @click="addCourse" class="green-button" id="save-course">Save</button>
      <button @click="clearAdd" class="grey-button" id="cancel-course">Cancel</button>
    </span>
  </div>
</template>

<script>
export default {
  name: "Add",
  data() {
    return {
      addVis: false
    };
  },
  methods: {
    showAdd() {
      this.addVis = !this.addVis;
    },
    clearAdd() {
      this.addVis = false;
      this.$refs['title'].value = '';
      this.$refs['semester'].value = '';
      this.$refs['grade'].value = '';
    },
    addCourse() {
      var course = {
        id: 0,
        name: this.$refs['title'].value,
        semester: this.$refs['semester'].value,
        grade: this.$refs['grade'].value
      };
      this.$emit("course", course);
      this.clearAdd();
    }
  }
};
</script>

<style scoped>
.blue-button {
  background-color: #2196f3;
  color: #ffffff;
  border: none;
  padding: 10px 20px;
}

.green-button {
  background-color: #69f378;
  color: #ffffff;
  border: none;
  padding: 10px 10px;
  margin-left: 5px;
}

.grey-button {
  background-color: #e1e8e6;
  color: #ffffff;
  border: none;
  padding: 10px 20px;
  margin-left: 5px;
}

.input {
  border: 1px solid #cccccc;
  padding: 10px 20px;
  min-width: 135px;
  margin-left: 5px;
}

#add-course {
  display: inline;
}
</style>