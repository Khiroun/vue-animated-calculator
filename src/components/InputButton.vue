<template>
  <input type="button" :value="value" @click="$emit('update-value', value)" />
</template>

<script>
export default {
  name: "InputButton",
  props: {
    value: String,
  },
};
</script>
