<template>
  <h5>Select dates:</h5>
  <datepicker v-model="model.date"></datepicker>
  <datepicker
    v-model="model.date2"
    placeholder="yyyy年MM月dd日"
    :format="'yyyy年MM月dd日'"
  ></datepicker>
  <datepicker v-model="model.date3" :style="{ width: '230px' }"></datepicker>
  <datepicker v-model="model.date3" @click="onClick"></datepicker>
  <pre
    >{{ model }}
  </pre>
</template>
<script>
//import { DatePicker } from '@progress/kendo-dateinputs-vue-wrapper';
import LcDatepicker from './LcDatepicker.vue';
import { ref } from 'vue';

export default {
  components: {
    datepicker: LcDatepicker,
  },
  setup() {
    const model = ref({});
    const onClick = () => {
      console.log('click');
    };
    return {
      model,
      onClick,
    };
  },
};
</script>
