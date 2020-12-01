<template>
  <div id="events">
    <div class="container">
      <div class="content">
        <EventItem class="event" title="Beyond the Valley 2020" subtitle="Melbourne, Sat 29th Jan 2020"/>
        <EventItem class="event" title="Beyond the Valley 2019 Summer Sessions" subtitle="Melbourne, Sat 29th Jan 2019"/>
        <EventItem class="event" title="Beyond the Valley 2018 Spring" subtitle="Melbourne, Sat 28th Sep 2018"/>
        <EventItem class="event" title="Beyond the Valley 2017 Summer" subtitle="Melbourne, Sat 29th Nov 2017"/>
        <EventItem class="event" title="Beyond the Valley Winter Festival 2017" subtitle="Melbourne, Sat 20th Jun 2017"/>
        <EventItem class="event" title="Beyond the Valley 2017" subtitle="Melbourne, Sat 29th Jan 2017"/>
        <EventItem class="event" title="Beyond the Valley 2016" subtitle="Melbourne, Sat 29th Jan 2016"/>
        <EventItem class="event" title="Beyond the Valley 2015" subtitle="Melbourne, Sat 29th Jan 2015"/>
        <EventItem class="event" title="Beyond the Valley 2014" subtitle="Melbourne, Sat 29th Jan 2014"/>
      </div>
    </div>
  </div>
</template>

<script>
import EventItem from './EventItem.vue'

export default {
  name: 'Events',
  components: {
    EventItem
  }
}
</script>

<style scoped lang="scss">
.container{
  width: 100%;
}
.content{
  display: grid;
  grid-gap: 0 15px;
  grid-template-columns: repeat(auto-fit, minmax(380px, 1fr));
  justify-items: center;
}
.event{
  max-width: 380px;
  width: 100%;
  margin-bottom: 31px;
  min-width: 302px;
  max-height: 315px;

  &:nth-child(3n+1){
    justify-self: start;
  }

  &:nth-child(3n+2){
    justify-self: center;
  }

  &:nth-child(3n+3){
    justify-self: end;
  }

}
</style>
