<template>
  <div>
    <nuxt/>
  </div>
</template>

<style>
@import url('https://fonts.googleapis.com/css?family=Dosis:200,300,400,500,600,700,800&display=swap');

html {
  font-family: 'Dosis', Roboto, "Helvetica Neue", Arial, sans-serif;
  font-size: 16px;
  word-spacing: 1px;
  -ms-text-size-adjust: 100%;
  -webkit-text-size-adjust: 100%;
  -moz-osx-font-smoothing: grayscale;
  -webkit-font-smoothing: antialiased;
  box-sizing: border-box;
}

*, *:before, *:after {
  box-sizing: border-box;
  margin: 0;
}

.button--yellow {
  display: inline-block;
  border-radius: 4px;
  border: 1px solid #fba617;
  color: #fba617;
  text-decoration: none;
  padding: 10px 30px;
}

.button--yellow:hover {
  color: #fff;
  background-color: #fba617;
}

.button--grey {
  display: inline-block;
  border-radius: 4px;
  border: 1px solid #35495e;
  color: #35495e;
  text-decoration: none;
  padding: 10px 30px;
  margin-left: 15px;
}

.button--grey:hover {
  color: #fff;
  background-color: #35495e;
}
</style>

