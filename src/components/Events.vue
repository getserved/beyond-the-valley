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
  display: flex;
}
.content{
  display: flex;
  flex-direction: row;
  flex-wrap: wrap;
  justify-content: space-between;
}
.event{
  max-width: 380px;
  flex: 1 1 33%;
  margin-bottom: 30px;
  min-width: 380px;
  min-height: 315px;
}
</style>
