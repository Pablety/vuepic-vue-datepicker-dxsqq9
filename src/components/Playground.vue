<template>
  <div>
    <h5>{{ date }}</h5>
    <hr />
    <Datepicker
      v-model="date"
      inline
      autoApply
      inlineWithInput
      :enableTimePicker="false"
      dark
      inputClassName="dp-custom-input"
      :allowedDates="allowedDates"
      locale="latam"
    />
  </div>
</template>

<script setup>
import { ref, computed } from 'vue';
import Datepicker from '@vuepic/vue-datepicker';
import '@vuepic/vue-datepicker/dist/main.css';
//allowedDates = computed(new Date())

const date = ref();

// For demo purposes, enable only today and tomorrow
const allowedDates = computed(() => {
  return [new Date(), new Date(new Date().setDate(new Date().getDate() + 1))];
});
</script>
