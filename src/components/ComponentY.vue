<template>
  <h3>ComponentY</h3>
  <small>RootComponentPropsAge</small>
  <p>age: <strong>{{ RootComponentPropsAge }}</strong></p>
</template>

<script>
export default {
  name: "ComponentY",
  props:
      {
        RootComponentPropsAge: [Number]
      }
}
</script>
