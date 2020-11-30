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
  width: auto;
  margin: 0;
  display: flex;
  flex-direction: row;

}
.header{
  color: $colorTextTitle;
  text-align: left;

  h2{
    margin: auto 0;
    font-size: 30px;
    line-height: 40px;
    font-weight: 400;
  }
}
.search{
  max-width: 300px;
  max-height: 50px;
  width: 300px;
  height: 50px;
  position: relative;

  &:before{
    content: "";
    display: block;
    width: 16px;
    height: 16px;
    position: absolute;
    left: 16px;
    top: 50%;
    transform: translateY(-50%);
    background-image: url('../assets/images/search.png');
    z-index: 2;
    pointer-events: none;
  }
}
.search-input{
  max-height: 50px;
  width: 253px;
  height: 48px;
  color: $colorTextInput;
  font-size: 14px;
  line-height: 18px;
  position: relative;
  padding: 0 0 0 45px;
  border-radius: 4px;
  border: 1px solid $colorLighterGrey;
  outline: none;
  position: relative;

  &:focus{
    color: $colorTextInputFocus;
    border: 1px solid $colorTextInputFocus;
    box-shadow: 0 0 0 3px $colorTextInputFocusShadow;
  }

  &::placeholder{
    color: $colorTextPlaceHolder;
  }
}
.event-btn{
  margin-left: 10px;
  max-width: 190px;
  min-width: 79px;
  width: 190px;
  height: 50px;
  color: white;
  font-weight: 500;
  position: relative;
  background-color: $colorBtn;
  border: 1px solid $colorBtnBorder;
  border-radius: 3px;
  outline: none;
  padding: 0;
  cursor: pointer;

  span{
    display: block;
    padding-left: 45px;
    font-size: 14px;
    line-height: 18px;
    text-align: left;

    &.small{
      display: none;
    }
  }

  &:hover{
    background-color: $colorBtnHover;
  }

  &:before{
    content: "";
    display: block;
    width: 16px;
    height: 16px;
    position: absolute;
    left: 21px;
    top: 50%;
    transform: translateY(-50%);
    background-image: url('../assets/images/add.png');
    z-index: 2;
    pointer-events: none;
  }
}
</style>
