<template>
  {{ fullName }}
  <input type="text" @input="setFName" />
  <input type="text" @input="setLName" />
</template>

<script>
import { ref, computed } from 'vue';

export default {
  setup() {
    const fName = ref('Peter');
    const lName = ref('Maier');

    function setFName(e) {
      fName.value = e.target.value;
    }

    function setLName(e) {
      lName.value = e.target.value;
    }

    const fullName = computed(function () {
      return fName.value + ' ' + lName.value;
    });

    return { fName, lName, fullName, setLName, setFName };
  },
};
</script>
