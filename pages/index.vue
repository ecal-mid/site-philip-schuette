<template lang="pug">
.site
  nav#menu
    a(href='/').home
      .arrow
  .wrapper
    .block
      .title
        h1 Workshop
        h2 With Philip Shuette
    .block
      h1 Sensory Augmentation & Brain Plasticity
      .description {{description}}
    .block
      .title
        h1 Abstract Data
        h3 Kylan Lüginbuhl & Evan
      img(src='img/poster.jpg')
    .block
      h3 text
    .block
      h1 New Function
      img(src='img/poster2.jpg')
    .block
      h3 text
    .block
      img(src='img/poster3.jpg')
    .block
      img(src='img/poster4.jpg')
    .block
      img(src='img/poster5.jpg')
    .block
      img(src='img/poster6.jpg')

</template>


<script>
import description from '@/static/description'
export default {
  data() {
    return {
      description
    }
  }
}
</script>

<style lang="sass">
@import url('https://fonts.googleapis.com/css?family=Rubik|Space+Mono')
body
  -webkit-font-smoothing: antialiased
  -moz-osx-font-smoothing: grayscale
  font-family: 'Rubik', sans-serif
  background-color: #ddd
  font-size: 2vh
  padding: 20px
.home
  display: inline-block
  width: 2.5em
  height: 2.5em
  padding: 0.5em
  position: relative
.arrow
  box-sizing: border-box
  width: 100%
  height: 100%
  border-left: solid black
  border-top: solid black
  transform: rotate(-45deg)
.wrapper
  width: 70%
  margin: auto
  display: flex
  flex-wrap: wrap
  .block
    width: 50%
    flex: 0 0 auto
    padding: 5px
    img
      width: 100%
      margin-bottom: -4px
#menu
  position: fixed
</style>

