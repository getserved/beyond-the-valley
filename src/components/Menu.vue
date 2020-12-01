<template>
  <div id="menu">
    <div ref="root" class="container" data-handler>
      <div class="menu-icon" @mouseenter="handleClick">
        <svg width="4px" height="16px" viewbox="0 0 4 16" version="1.1" xmlns:xlink="http://www.w3.org/1999/xlink" xmlns="http://www.w3.org/2000/svg">
          <g id="more" transform="matrix(-4.371139E-08 -1 1 -4.371139E-08 0 16)">
            <path d="M2 12C3.1 12 4 12.9 4 14C4 15.1 3.1 16 2 16C0.9 16 0 15.1 0 14C0 12.9 0.9 12 2 12L2 12ZM2 10C0.9 10 0 9.1 0 8C0 6.9 0.9 6 2 6C3.1 6 4 6.9 4 8C4 9.1 3.1 10 2 10L2 10ZM2 4C0.9 4 0 3.1 0 2C0 0.9 0.9 0 2 0C3.1 0 4 0.9 4 2C4 3.1 3.1 4 2 4L2 4Z" transform="matrix(-4.371139E-08 1 1 4.371139E-08 0 0)" id="Shape" fill="#FFFFFF" fill-rule="evenodd" stroke="none" />
          </g>
        </svg>
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
  props:{
    isMenuHover: {
      type: Boolean,
      default: false
    }
  },
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
      this.$parent.setMenuHover(true);

      let checkMouseLeave = (e) => {
        if (rootRef
            && !rootRef.contains(e.target)) {
              vm.active = false;
              this.$parent.setMenuHover(false);
              window.removeEventListener('mousemove', checkMouseLeave)
            }
        }
        window.addEventListener('mousemove', checkMouseLeave)
    },
    handleMouseleave: function () {
      this.active = false;
      this.$parent.setMenuHover(false);
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
  top: 35px;
  max-width: 203px;
  width: 203px;
  max-height: 223px;
  height: 223px;
  background-color: white;
  border-radius: 5px;
  border: 1px solid $colorMenuHoverBorder;
  box-shadow: 0 2px 6px 0 $colorMenuShadow;

  &.active{
    display: flex;
    flex-direction: column;

    &:before {
      content: url("../assets/images/Triangle.svg?inline");
      position: absolute;
      right: 11px;
      top: -13px;

      z-index:5;
    }
  }

  .menu-content{
    position:relative;
    border-radius: 5px;
    background-color: white;
    padding: 15px 0 8px 0;
    z-index:5;
  }

  .menu-item{
    max-height: 40px;
    height: 40px;
    padding-left: 20px;
    padding-right: 20px;
    background: white;
    display: flex;
    position: relative;
    z-index: 5;

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
}
</style>
