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
  margin-top: 35px;
}
/*
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
*/
@media only screen and (max-width: 1372px) {
  body{
    margin: 0 8px;
  }
  #events > .container{
    max-height: 100%;
    min-height: auto;
  }
  #events .event:nth-child(3n+2){
    margin-left: 10px;
    margin-right: 10px;
  }
  #events  .event{
    flex: 1 1 30%;
    min-width: 200px;
    min-height: auto;
  }
  #app > .container{
    margin: 0 36px;

    > .content{
      max-width: 1230px;
      width: 100%;
      margin: auto;
    }
  }
}

@media only screen and (max-width: 828px) {
  #events{
    .content{
      justify-content: center;
    }

    .event{
      flex: 1 1 45%;
    }
  }
  #events .event:nth-child(3n+2){
    margin-left: 0px;
    margin-right: 0px;
  }
  #events .event:nth-child(2n){
    margin-left: 10px;
  }
  #events .event:nth-child(2n+1){
    margin-right: 10px;
  }
  #form .container{
    .event-btn{
      width: 140px;

      &:before{
        display: none;
      }
    }

    .search{
      width: 100%;
      .search-input{
        width: calc(100% - 45px);
        min-width: 100px;
      }
    }


    .event-btn{
      padding: 0;

      span{
        padding: 0;
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
  #app{
    margin-top: 30px;
  }

  #app > .container{
    margin: 0 5.346535% 0 4.753%;
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
      padding-bottom:19px;
    }

    .event-btn{
      width: 141px;

      &:before{
        display: none;
      }
    }

    .search{
      width: 100%;
      .search-input{
        width: calc(100% - 46px);
        max-width: 253px;
        min-width: 100px;
      }
    }

    .content{
      justify-content: space-between;
    }
    .event-btn{
      padding: 0;

      span{
        padding: 0;
      }

      .small{
        display: inline-block;
      }
      .large{
        display: none;
      }
    }
  }
  #body{
    margin-top: 30px;
  }
  #events > .container{
    flex-direction: column;
    justify-content: center;
    overflow-x: hidden;

    > .content{
      max-width: 380px;
      min-width: 320px;
      width: 380px;
      margin: auto;
    }

    .menu{
      right: 20px;
    }
  }
  #events .event:nth-child(2n){
    margin-left: 0px;
  }
  #events .event:nth-child(2n+1){
    margin-right: 0px;
  }
}
@media only screen and (max-width: 452px) {
  $header-margin: 0 0;
  #app > .container{
    margin: 0px;
  }
  #events{
    .event{
      min-width: 302px;
      min-height: 250px;
    }
    > .container > .content{
        min-width: 100%;
        max-width: 100%;
        width: 100%;
    }

    > .container .menu{
      top: 14px;
      right: 14px;
    }

    .container{
      max-width: 100%;
    }

    .inner-content{
      margin: 24px;
    }

    .title span{
      max-width: 100%;
    }
  }
}
@media only screen and (max-width: 320px) {
    #app{
      margin-top: 24px;
    }
    #header{
      margin: 0 0;
      padding-bottom: 30px;
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
          width: calc(100% - 12px);
          padding-left: 12px;
        }
        &:before{
          display: none;
        }
      }
    }
    #events{
      max-width: 302px;
      width: 100%;
      margin: auto;
    }
    #events > .container{


      .event{
        margin-bottom: 20px;
        min-width: 302px;
        min-height: 250px;
      }

      .inner-content{
        margin: 16px 24px 18px 24px;
        max-width: 245px;
      }

      .icon{
        width: 22px;
        height: 22px;
      }
    }

}
</style>
