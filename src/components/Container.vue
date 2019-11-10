<template>
  <section id="container">
    <section id="main">
      <div class="content">
        <Profile v-show="toggle" />
        <Courses v-show="!toggle" />
      </div>
      <div class="controls">
        <button
          @click="changeToCourse"
          id="profile-button"
          class="static"
          :class="{active: isActive, pill:true}"
        >Profile</button>
        <button
          @click="changeToProfile"
          id="courses-button"
          class="static"
          :class="{pill: true, active:!isActive}"
        >Courses</button>
      </div>
    </section>
  </section>
</template>

<script>
import Profile from "./Profile";
import Courses from "./Courses";

export default {
  name: "Container",
  components: {
    Profile,
    Courses
  },
  data() {
    return {
      toggle: true,
      isActive: true
    };
  },
  methods: {
    changeToCourse() {
      this.toggle = true;
      this.isActive = true;
    },
    changeToProfile() {
      this.toggle = false;
      this.isActive = false;
    }
  }
};
</script>

<style scoped>
main {
  position: relative;
  min-height: 100%;
  padding-bottom: 110px;
}

.content .tab.active {
  display: block;
}

.content .tab {
  display: block;
}

#container {
  width: 80%;
  max-width: 900px;
  min-width: 320px;
  padding: 15px;
  background-color: #ffffff;
  margin: 0 auto;
}

.content {
  padding: 10px;
  border: 1px solid #cbcbcb;
}

.controls .pill {
  border: 1px solid #cbcbcb;
  background-color: #eaeaea;
  padding: 10px;
  border-bottom-left-radius: 4px;
  border-bottom-right-radius: 4px;
  border-top: none;
  margin-top: -1px;
  outline: none !important;
}

.controls .pill.active {
  background-color: #ffffff;
  border-top: 1px solid #ffffff;
}

.controls .pill:hover {
  cursor: pointer;
}
</style>