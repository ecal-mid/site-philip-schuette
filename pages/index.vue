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
    template(
      v-for='project in content.projects'
    )
      .block
        .title
          h1 {{project.title}}
        .students
          h5(v-for='student in project.students') {{student}}
        .poster
          img(:src='project.poster')
      .block.slider
        .swiper-wrapper
          template(v-for='imgTmp in project.img')
            .swiper-slide(
              v-for='index in (imgTmp.recursive[1] - imgTmp.recursive[0])'
              v-if='imgTmp.recursive'
              :style='{"background-image": "url(\'"+ (imgTmp.path + recursiveName(index + 1, imgTmp.recursiveName)) + "\')"}'
            )
      
</template>


<script>
import description from '@/static/description'
import content from '@/static/content'
const Swiper = require('swiper').default
export default {
  data() {
    return {
      content,
      description
    }
  },
  mounted() {
    console.log(Swiper)
    const mySwiper = new Swiper ('.slider', {
      // Optional parameters
      direction: 'horizontal',
      loop: true
    })
  },
  methods: {
    recursiveName(index, name) {
      const splitName = name.split('/%num/%')
      console.log(splitName)
      return splitName[0] + index + splitName[1]
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
.slider
  .swiper-wrapper
    width: 100%
    height: 100%
    .swiper-slide
      float: left
      width: 100%
      height: 100%
      background-color: grey
      background-position: 50% 50%
      background-size: contain
      background-repeat: no-repeat
#menu
  position: fixed
</style>

