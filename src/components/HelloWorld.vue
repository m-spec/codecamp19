<template>
  <video id="camera" autoplay></video>
</template>

<script>
export default {
  name: "HelloWorld",
  props: {
    msg: String
  }
};

navigator.mediaDevices
  .getUserMedia({ video: true })
  .then(function(stream) {
    document.getElementById("camera").srcObject = stream;
  })
  .catch(function() {
    alert("could not connect stream");
  });
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
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
</style>
