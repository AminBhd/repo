<template>
  <div id="header">

    <div class="logo"><p>Portfo<span>lio</span></p></div>
    <div class="nav-list">
      <ul>
        <li><a href="#home-page">Home</a></li>
        <li><a href="#">About</a></li>
        <li><a href="#">Services</a></li>
        <li><a href="#">Projects</a></li>
        <li><a href="#">Contacts</a></li>
      </ul>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Header',
  props: {
  },
  data() {
    return {
      developer: "Amine Baheddi",
      age: 20
    }
  },
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
#header{
  height: 60px;
  width: 100%;
  display: flex;
  justify-content: space-between;
  margin-bottom: 2px;
  box-shadow: 1px 1px 5px rgba(0, 0, 0, 0.57);
}

.logo {
  padding-left: 15px;
}

ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a{
  text-decoration: none;
  color: #000;
}

</style>
