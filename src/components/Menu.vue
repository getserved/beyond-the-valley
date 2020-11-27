<template>
  <div id="menu">
    <div ref="root" class="container" data-handler>
      <div class="menu-icon" @mouseenter="handleClick">
        <img :src="require('../assets/images/more.png')"/>
      </div>
      <div class="menu-mouse-range">
      </div>
      <div class="menu-layout" :class="{active: isActive}" @mouseleave="handleMouseleave">
          <div class="menu-content" >
            <div class="menu-item">
              <span>Create campaign</span>
            </div>
            <div class="menu-item">
              <span>Import ticket sales</span>
            </div>
            <div class="menu-item">
              <span>Edit event details</span>
            </div>
            <div class="menu-item">
              <span>Merge event</span>
            </div>
            <div class="menu-item">
              <span>Delete event</span>
            </div>
          </div>
      </div>
    </div>
  </div>
</template>

<script>

export default {
  name: 'Menu',
  components: {

  },
  data () {
    return {
      active: false
    }
  },
  computed:{
    isActive () {
      return this.active;
    }
  },
  mounted: function () {

  },
  methods: {
    handleClick: function () {
      this.active = true;
      const vm = this;
      const rootRef = this.$refs.root;

      let checkMouseLeave = (e) => {
        if (rootRef
            && !rootRef.contains(e.target)) {
              vm.active = false;
              window.removeEventListener('mousemove', checkMouseLeave)
            }
        }
        window.addEventListener('mousemove', checkMouseLeave)
    },
    handleMouseleave: function () {
      this.active = false;
    }
  }
}
</script>

<style scoped lang="scss">
#menu{
  cursor: pointer;
}
.container{
  position: relative;
}
.menu-icon{
  position: relative;
  z-index: 10;
}
.menu-layout{
  display: none;
  position: absolute;
  right: -33px;
  top: 34px;
  max-width: 205px;
  width: 205px;
  max-height: 200px;
  height: 200px;
  padding: 24px 0;
  background-color: white;
  border-radius: 5px;
  border: 1px solid $colorLighterGrey;
  box-shadow: 0 2px 6px 0 $colorMenuShadow;

  &.active{
    display: flex;
    flex-direction: column;
  }

  .menu-content{

  }

  .menu-item{
    -webkit-touch-callout: none;
    -webkit-user-select: none;
    -khtml-user-select: none;
    -moz-user-select: none;
    -ms-user-select: none;
    user-select: none;
    -webkit-tap-highlight-color: transparent;
    max-height: 40px;
    height: 40px;
    padding-left: 24px;
    padding-right: 24px;
    background: white;
    display: flex;


    span{
      color: $colorMenuText;
      display: inline-block;
      font-size: 14px;
      line-height: 20px;
      margin: auto 0;
      text-align: left;
    }

    &:hover{
      background: $colorMenuHover;

      span{
        color: $colorMenuHoverText;
      }

    }
  }

  &:before {
    position: absolute;
    top: -5px;
    right: 28px;
    content: '';
    width: 10px;
    height: 10px;
    background: white;
    transform: rotate(-45deg);
    border: 1px solid $colorLighterGrey;
    box-shadow: 0 2px 6px 0 $colorMenuShadow;
  }
  &:after {
    position: absolute;
    top: 0px;
    right: 24px;
    content: '';
    width: 20px;
    height: 20px;
    background: white;
  }
}
.menu-mouse-range{
  padding-top: 34px;
  position: absolute;
  right: -34px;
  top: -10px;
  max-width: 205px;
  width: 205px;
  max-height: 230px;
  height: 230px;
  background-color: white;
  border-radius: 5px;
  opacity: 0;
  border: 1px solid $colorLighterGrey;
  box-shadow: 0 2px 6px 0 $colorMenuShadow;
}
</style>
