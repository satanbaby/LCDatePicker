<template>
  <!-- <kendo-datepicker
    ref="self"
    :format="'yyyy/MM/dd'"
    @close="close"
    @click="toggle"
    placeholder="yyyy/MM/dd"
  ></kendo-datepicker> -->
  <kendo-datepicker
    ref="self"
    :format="'yyyy/MM/dd'"
    placeholder="yyyy/MM/dd"
    @close="close"
    @click="toggle"
    v-bind="$attrs"
    v-on="$listeners"
  ></kendo-datepicker>
</template>
<script>
import { DatePicker } from '@progress/kendo-dateinputs-vue-wrapper';
import { ref, props } from 'vue';
export default {
  components: {
    'kendo-datepicker': DatePicker,
  },
  setup() {
    const self = ref(null);

    let status = false;
    const toggle = () => {
      status = !status;
      status
        ? self.value.kendoWidget().open()
        : self.value.kendoWidget().close();
    };

    const close = () => {
      // reset status
      status = false;
    };

    return {
      ...DatePicker,
      self,
      close,
      toggle,
    };
  },
};
</script>
