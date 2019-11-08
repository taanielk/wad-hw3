<template>
  <main id="app">
    <header>
      <strong>Welcome to your dashboard!</strong>
    </header>
    <Container />
    <footer>
      <ul class="links">
        <li>
          <a href="https://ois2.ut.ee/" target="_blank">OIS</a>
        </li>
        <li>
          <a href="https://courses.cs.ut.ee/" target="_blank">Courses</a>
        </li>
      </ul>
    </footer>
  </main>
</template>
<script>
import Container from "./components/Container";

export default {
  name: "app",
  components: {
    Container
  }
};
</script>

<style>
* {
  box-sizing: border-box;
  font-family: "Livvic", sans-serif;
}

html,
body {
  padding: 0;
  margin: 0;
  width: 100%;
  height: 100%;
  background-color: #eaeaea;
}

header {
  padding: 20px;
  background-color: #2196f3;
  color: #ffffff;
  text-align: center;
  margin-bottom: 10px;
  height: 60px;
}

footer {
  padding: 30px 0;
  background-color: #607d8b;
  margin-top: 10px;
  height: 100px;
  position: absolute;
  bottom: 0;
  width: 100%;
}

footer .links {
  display: block;
  width: 100%;
  max-width: 200px;
  margin: 0 auto;
  color: #acd7ff;
  font-size: 11px;
}

footer .links a {
  text-decoration: none;
  color: #acd7ff;
}

footer .links a:hover {
  text-decoration: underline;
}
</style>
