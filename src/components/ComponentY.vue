<template>
  <h5>ComponentY</h5>
  <p>value: <strong>{{ componentValue }}</strong></p>
</template>

<script>
export default {
  name: "ComponentY",
  props:
      {
        componentValue: [Number, String]
      }
}
</script>
