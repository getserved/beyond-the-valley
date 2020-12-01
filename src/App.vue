<template>
  <div id="app">
    <div class="container">
      <div class="content">
        <div id="header" class="header">
          <Form />
        </div>
        <div id="body" class="body">
          <Events/>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import Form from './components/Form.vue'
import Events from './components/Events.vue'

export default {
  name: 'App',
  components: {
    Form,
    Events
  }
}
</script>

<style lang="scss">
@font-face {
  font-family: "Graphik";
  src: url(./assets/fonts/Graphik-Medium.ttf) format("truetype"),
    url(./assets/fonts/Graphik-Medium.woff) format("woff"),
    url(./assets/fonts/Graphik-Medium.woff2) format("woff2"),
    url(./assets/fonts/Graphik-Medium.eot) format("eot")
  ;
  font-weight: 500;
  font-style: normal;
}
@font-face {
  font-family: "Graphik";
  src: url(./assets/fonts/Graphik-Regular.ttf) format("truetype"),
    url(./assets/fonts/Graphik-Regular.woff) format("woff"),
    url(./assets/fonts/Graphik-Regular.woff2) format("woff2"),
    url(./assets/fonts/Graphik-Regular.eot) format("eot")
  ;
  font-weight: 400;
  font-style: normal;
}
@font-face {
  font-family: "Graphik";
  src: url(./assets/fonts/Graphik-Light.ttf) format("truetype"),
    url(./assets/fonts/Graphik-Light.woff) format("woff"),
    url(./assets/fonts/Graphik-Light.woff2) format("woff2"),
    url(./assets/fonts/Graphik-Light.eot) format("eot")
  ;
  font-weight: 300;
  font-style: normal;
}
html{
  background-color: $colorPage;
  overflow-x: hidden;
  width: 100%;
  height: 100%;
  font-family: 'Graphik';
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  font-size: 16px;
}
#app {
  text-align: center;
  color: #2c3e50;
  margin-top: 42px;
}

body{
  margin: 0 9px;
}

#app > .container{
  display: flex;

  > .content{
    max-width: 1230px;
    width: 100%;
    margin: auto;
  }
}
#header{
  padding-bottom: 33px;
  position: relative;

  &:after{
    content: "";
    width: 99.1870%;
    position: absolute;
    left: 0;
    bottom: 0;
    height: 1px;
    background-color: $colorLighterGrey;
  }
}
#body{
  margin-top: 34px;
}
a, *:focus,*:hover{
  outline: none;
  -webkit-touch-callout: none;
  -webkit-user-select: none;
  -khtml-user-select: none;
  -moz-user-select: none;
  -ms-user-select: none;
  user-select: none;
  -webkit-tap-highlight-color: transparent;
  -webkit-tap-highlight-color: rgba(0, 0, 0, 0);
}
@media only screen and (max-width: 1373px) {
  #app > .container{

    > .content{
      margin: auto auto auto 62px;
    }
  }

}
@media only screen and (max-width: 1210px) {
  #app > .container{

    > .content{
      margin: auto;
    }
  }
  #events > .container > .content{
    grid-template-columns: repeat(auto-fit, minmax(302px, 1fr));

    > .event{
      min-width: 302px;
    }
  }
}
@media only screen and (max-width: 1024px) {
  #events > .container > .content{
    grid-template-columns: repeat(2, 1fr);

    > .event{

      &:nth-child(3n+1){
        justify-self: auto;
      }

      &:nth-child(3n+2){
        justify-self: auto;
      }

      &:nth-child(3n+3){
        justify-self: auto;
      }

      &:nth-child(2n+1){
        justify-self: start;
      }

      &:nth-child(2n+2){
        justify-self: end;
      }
    }
  }
}
@media only screen and (max-width: 764px) {
  #events > .container > .content{
    grid-template-columns: repeat(1, 1fr);

    > .event{

      &:nth-child(3n+1){
        justify-self: auto;
      }

      &:nth-child(3n+2){
        justify-self: auto;
      }

      &:nth-child(3n+3){
        justify-self: auto;
      }

      &:nth-child(2n+1){
        justify-self: auto;
      }

      &:nth-child(2n+2){
        justify-self: auto;
      }
    }
  }

  #form .container{
    .search{
      min-width: 200px;
      margin-left: 10px;
    }
    .event-btn{
      width: 141px;

      &:before{
        display: none;
      }
    }

    .event-btn{
      padding: 0;

      span{
        padding: 0;
        max-width: 115px;
        text-align: center;
      }

      .small{
        display: inline-block;
      }
      .large{
        display: none;
      }
    }
  }
}
@media only screen and (max-width: 521px) {
  body{
    margin: 0 9px;
  }
  #app{
    margin-top: 30px;
  }

  #app > .container{
    margin: 0 26px;
  }
  #header{
    padding-bottom: 31px;

    &:after{
      width: 100%;
    }
  }

  #form .container{
    width: 100%;
    flex-direction: column;
    width: 100%;


    .header{
      margin-left: -3px;
      margin-top: 0px;
      padding-bottom: 26px;

      h2{
        margin-top: 1px;
        max-width: 374px;
        line-height: 33px;
      }
    }

    .search{
      width: 100%;
      margin-left: 0px;

      .search-input{
        max-width: 300px;
        min-width: 100px;
        line-height: 15px;

      }
    }

    .content{
      justify-content: space-between;
    }

  }
  #body{
    margin-top: 30px;
  }
  #events > .container > .content{
    grid-template-columns: repeat(1, 1fr);
  }
}
@media only screen and (max-width: 440px) {
  #app{
    margin-top: 24px;

    > .container{
      margin: 0;
    }
  }
  #header{
    margin: 0 0;
  }
  #body{
    margin-top: 32px;
  }
  #form .container{
    .header{
      padding-bottom: 13px;
    }

    .event-btn {
      max-wdith: 79px;
      min-width: 79px;
      width: 79px;
    }

    .search{
      .search-input{
        width: 100%;
        padding-left: 12px;
        padding-top: 2px;
      }
      &:before{
        display: none;
      }
    }
  }
}
@media only screen and (max-width: 320px) {
    #form .container{
      .event-btn .small{
        width: 100%;
        max-width: 64px;
        margin-left: 2px;
        margin-top: -1px;
        text-align: center;
      }
    }
    #form .container .header{
      padding-bottom: 20px;
    }
    #events{
      max-width: 302px;
      width: 100%;
      margin: auto;
    }
    #events > .container{

      .content{
        max-width: 302px;
        width: 100%;
      }

      .event{
        margin-bottom: 25px;
        min-width: 302px;
        max-height: 250px;
        min-height: 250px;
      }

      .bg-container{
        height: 162.7px;
      }

      .inner-content{
        padding: 16.47px 23.84px 18px 23.84px;
        max-width: 235px;

        .title{
          margin-bottom: 2.97px;
        }
      }

      .icon{
        width: 23.84px;
        height: 23.81px;
        left: 23.84px;
        display: flex;

        .svg-wrapper{
          margin:auto;


          &:before {
            content: url("./assets/images/logo-s.svg?inline");
            position: absolute;
            transform: translate(-50%, -50%);
            z-index:5;
          }
        }

        svg{

            width: 100%;
            height: 100%;
        }
      }

      .menu{
        right: 14px;
        top: 14px;
      }
    }
}
</style>
