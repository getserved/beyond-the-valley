<template>
  <div id="event-item">
    <div class="container" :class="{menuHover: isMenuHover}">
      <div class="content">
        <div class="bg-container">
          <div class="view-event">
            <span>View event</span>
          </div>
          <div class="icon">
            <img src="../assets/images/icon.png"/>
          </div>
        </div>
        <div class="inner-content">
          <div class="title">
            <span>{{title}}</span>
          </div>
          <div class="subtitle">
            <span>{{subtitle}}</span>
          </div>
        </div>
        <div class="menu" >
          <Menu />
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import Menu from './Menu.vue'

export default {
  name: 'EventItem',
  props: {
    background: String,
    title: String,
    subtitle: String,
  },
  data(){
    return {
      isMenuHover: false
    }
  },
  components: {
    Menu
  },
  methods: {
    setMenuHover: function(val){
      this.isMenuHover = val;
    }
  }
}
</script>

<style scoped lang="scss">
.container{
  max-width: 380px;
  max-height: 315px;
  min-height: 250px;
  width: 100%;
  height: 100%;
  background-color: white;
  text-align: left;
  position: relative;
  border-radius: 4px;

  &:before{
    content: "";
    width: calc(100% - 2px);
    height: calc(100% - 2px);
    position: absolute;
    top: 0px;
    left: 0px;
    border-radius: 4px;
    border: 1px solid $colorLighterGrey;
  }

  &:hover:not(.menuHover){
    box-shadow: 2px 0px 40px 0px $colorShadow;

    > .content > .bg-container{

      &:after{
        opacity: .9;
      }

      > .view-event{
        display: flex;
      }
    }
  }
}

.content{
  height: 100%;

  > .bg-container:after{
    opacity: 0;
    transition: .3s opacity ease-in-out;
    content: "";
    position: absolute;
    width: 100%;
    height: 100%;
    top: 0;
    left: 0;
    z-index: 3;
    background-color: $colorEventHover;
    display: block;
    border-top-left-radius: 4px;
    border-top-right-radius: 4px;
  }


}

.bg-container{
  background-color: #666666;
  background-image: url('../assets/images/bg.jpg');
  background-size: cover;
  background-position: center;
  position: relative;
  border-top-left-radius: 4px;
  border-top-right-radius: 4px;
  width: 100%;

  .view-event{
    display: flex;
    max-width: 120px;
    width: 120px;
    max-height: 40px;
    height: 40px;
    font-size: 14px;
    line-height: 18px;
    color: white;
    font-weight: 500;
    border: 1px solid white;
    border-radius: 3px;
    position: absolute;
    left: 50%;
    top: 50%;
    transform: translate(-50%, -50%);
    text-align: center;
    display: none;
    z-index: 5;
    cursor: pointer;

    span{
      margin: auto;
    }
  }

  &:before {
    content: '';
    display: block;
    padding: 53.95% 0 0;
  }

  .icon{
    display: flex;
    position: absolute;
    left: 28px;
    bottom: 0px;
    transform: translateY(50%);
    max-width: 28px;
    max-height: 28px;
    width: 28px;
    height: 28px;
    background-color: white;
    border: 1px solid $colorLighterGrey;
    border-radius: 50%;
    pointer-events: none;
    z-index: 5;

    img{
      margin: auto auto;
    }
  }
}

.inner-content{
  max-width: 320px;
  margin: 24px 30px 30px 30px;
}
.title{
  font-size: 20px;
  line-height: 25px;
  color: $colorTextTitle;
  max-width: 320px;

  span{
    max-width: 320px;
    display: block;
    overflow: hidden;
    text-overflow: ellipsis;
    white-space: nowrap;
  }
}

.subtitle{
  font-size: 16px;
  line-height: 25px;
  color: $colorTextSubtitle;

  span{
    max-width: 320px;
    display: block;
    overflow: hidden;
    text-overflow: ellipsis;
    white-space: nowrap;
  }
}

.menu{
  width: auto;
  height: auto;
  position: absolute;
  right: 24px;
  top: 20px;
  cursor: pointer;
  z-index: 5;
}
</style>
