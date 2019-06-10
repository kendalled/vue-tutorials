<template>
  <div class="hello">
    <header class="header">
        <img alt="Vue logo" src="../../assets/logo.png" class="pulse">
        <h1>{{ msg }}, Kendall.</h1>
    </header>
    
    
    
  </div>
</template>

<script>
export default {
  name: 'Header',
  props: {
    msg: String
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.pulse {
  max-width: 5rem;
  padding: 1rem;
  border-radius: 5%;
  background: #fff;
  cursor: pointer;
  box-shadow: 0 0 0 (66, 185, 131, 0.6);
  animation: pulse 1.5s infinite;
}
.pulse:hover {
  animation: none;
}

@-webkit-keyframes pulse {
  0% {
    -webkit-box-shadow: 0 0 0 0 rgba(66, 185, 131, 0.6);
  }
  70% {
      -webkit-box-shadow: 0 0 0 10px rgba(66, 185, 131, 0);
  }
  100% {
      -webkit-box-shadow: 0 0 0 0 rgba(66, 185, 131, 0);
  }
}
@keyframes pulse {
  0% {
    -moz-box-shadow: 0 0 0 0 rgba(66, 185, 131, 0.6);
    box-shadow: 0 0 0 0 rgba(66, 185, 131, 0.6);
  }
  70% {
      -moz-box-shadow: 0 0 0 10px rgba(66, 185, 131, 0);
      box-shadow: 0 0 0 10px rgba(66, 185, 131, 0);
  }
  100% {
      -moz-box-shadow: 0 0 0 0 rgba(66, 185, 131, 0);
      box-shadow: 0 0 0 0 rgba(66, 185, 131, 0);
  }
}
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}

.header {
        background: #333;
        color: #fff;
        text-align: center;
        padding: 1.5rem;
        margin-top: 1rem;
        border-radius: 12px;
    }
    .header a {
        color: #fff;
        padding-right: 1rem;
    }
</style>
