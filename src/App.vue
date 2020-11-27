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
}
#app {
  font-family: 'Graphick';
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
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
    width: 100%;
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

@media only screen and (max-width: 792px) {
  #events{
    .content{
      justify-content: center;
    }
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
  body{
    margin: 0 8px;
  }
  $header-margin: 0 5.37428vw;
  #header{
    margin: $header-margin;
  }

  #form .container{
    width: 100%;
    flex-direction: column;
    width: 100%;


    .header{
      padding-bottom:20px;
    }

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
}
@media only screen and (max-width: 380px) {
  $header-margin: 0 0;
  #header{
    margin: $header-margin;
  }
  #events{
    > .container > .content{
        min-width: 100%;
        max-width: 100%;
        width: 100%;
    }

    .container{
      max-width: 100%;
      width: calc(100% - 2px);
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
        padding-bottom: 12px;
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
    #events > .container{
      .event{
        margin-bottom: 20px;
        min-width: 300px;
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
      .menu{
        right: 12px;
      }
    }

}
</style>
