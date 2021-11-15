<template>
  <h5>ComponentX</h5>
  <p>value: <strong>{{ componentValue }}</strong></p>
</template>

<script>
export default {
  name: "ComponentX",
  props:
      {
        componentValue: [Number, String]
      }
}
</script>
