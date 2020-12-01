<template>
  <div id="form">
    <div class="container">
      <div class="header">
        <h2>Events</h2>
      </div>
      <div class="content">
        <div class="search">
          <input class="search-input" placeholder="Search 9 events..." type="text" />
        </div>
        <div class="create-new-event">
          <button class="event-btn">
            <span class='large'>Create new event</span>
            <span class='small'>Create</span>
          </button>
        </div>
      </div>
    </div>
  </div>
</template>

<script>

export default {
  name: 'Form',
  components: {

  }
}
</script>

<style scoped lang="scss">
.container{
  display: flex;
  flex-direction: row;
  justify-content: space-between;
}
.content{
  width: 100%;
  margin: 0;
  display: flex;
  flex-direction: row;
  justify-content: flex-end;
}
.header{
  color: $colorTextTitle;
  text-align: left;
  margin-top: 8px;

  h2{
    margin: auto 0;
    font-size: 30px;
    line-height: 33px;
    font-weight: 400;
  }
}
.search{
  max-width: 300px;
  min-width: 300px;
  max-height: 50px;
  width: 100%;
  height: 50px;
  position: relative;

  &:before{
    content: url("../assets/images/search.svg?inline");
    display: block;
    width: 16px;
    height: 16px;
    position: absolute;
    left: 17px;
    top: 50%;
    transform: translateY(-50%);
    z-index: 2;
    pointer-events: none;
  }
}
.search-input{
  -webkit-box-sizing: border-box; /* Safari/Chrome, other WebKit */
  -moz-box-sizing: border-box;    /* Firefox, other Gecko */
  box-sizing: border-box;
  max-height: 50px;
  max-width: 302px;
  width: 100%;
  height: 50px;
  color: $colorTextInput;
  font-size: 14px;
  font-weight: 400;
  line-height: 50px;
  position: relative;
  padding: 3px 0 0 44px;
  border-radius: 3px;
  border: 1px solid $colorLighterGrey;
  outline: none;
  position: relative;
  letter-spacing: 0.2px;

  &:focus{
    color: $colorTextInputTextFocus;
    border: 1px solid $colorTextInputFocus;
    box-shadow: 0 0 0 3px $colorTextInputFocusShadow;
  }

  &::placeholder{
    color: $colorTextPlaceHolder;
  }
}
.event-btn{
  -webkit-box-sizing: border-box; /* Safari/Chrome, other WebKit */
  -moz-box-sizing: border-box;    /* Firefox, other Gecko */
  box-sizing: border-box;
  margin-left: 10px;
  max-width: 190px;
  min-width: 79px;
  width: 190px;
  height: 50px;
  color: white;
  font-weight: 500;
  position: relative;
  background-color: $colorBtn;
  border: 1px solid $colorBtn;
  border-radius: 3px;
  outline: none;
  padding: 0;
  cursor: pointer;

  span{
    display: block;
    padding-left: 46px;
    font-size: 14px;
    line-height: 50px;
    text-align: left;
    letter-spacing: 0.4px;
    max-width: 154px;
    width: 100%;

    &.small{
      display: none;
    }
  }

  &:hover{
    background-color: $colorBtnHover;
    border: 1px solid $colorBtnHover;
  }

  &:before{
    content: url("../assets/images/add.svg?inline");
    display: block;
    width: 16px;
    height: 16px;
    position: absolute;
    left: 20px;
    top: 15px;
    z-index: 2;
    pointer-events: none;
  }
}
</style>
