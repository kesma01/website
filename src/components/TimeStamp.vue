<template>
  <div class="time-stamp">
    <p v-if="exportTime">
      Osveženo <span>{{ exportTime | formatDate('d. MMMM yyyy') }}</span> ob
      <span>{{ exportTime | formatDate('HH:mm') }}</span>
    </p>
    <p v-else>
      
    </p>
  </div>
</template>
<script>
import { mapState } from 'vuex';

export default {
  computed: {
    ...mapState('stats', ['exportTime']),
  },
};
</script>

<style scoped lang="scss">
.time-stamp {
  min-height: 41px;
  margin-bottom: 48px;
  background: #fff;
  border-bottom: 1px solid rgba(0, 0, 0, 0.13);

  p {
    margin: 0;
    padding: 8px 15px;
    line-height: 1.85;
    font-size: 13px;
    color: rgba($color: #000000, $alpha: 0.5);

    @media only screen and (min-width: 768px) {
      padding: 8px 32px;
    }
  }
}
</style>
