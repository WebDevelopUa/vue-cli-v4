<template>
  <h3>ComponentX</h3>
  <small>RootComponentPropsName</small>
  <p>name: <strong>{{ RootComponentPropsName }}</strong></p>
  <small> RootComponentPropsAge</small>
  <p>age: <strong>{{ RootComponentPropsAge }}</strong></p>

  <p v-if="RootComponentPropsAge > 25">over 25</p>
  <p v-else-if="RootComponentPropsAge === 25">25</p>
  <p v-else> under 25</p>

  <!-- Button #2 with Emitting (trigger) custom Events to avoid  -->
  <!-- error Unexpected mutation of "RootComponentPropsAge" prop  vue/no-mutating-props  -->
  <!-- update props from a child component  -->
  <button type="button"
          @click="onClickAgeReduce">
    RootComponentPropsAge--
  </button>

  <!-- Emit event (recommended) -->
  <!-- easier to debug using Vue Dev Tools / Component events -->
  <button type="button"
          @click="onClickAgeReset">
    RootComponentPropsAge = 0
  </button>

  <!-- Call the function inside the parent component to get access to the data-->
  <button type="button"
          @click="resetAgeCallbackFn(0)">
    resetAgeCallbackFn: 0
  </button>

  <h6>ageDoubled (computed): {{ ageDoubled }}</h6>

</template>

<!-- Validator functions runs before the instance of the component is created -->
<script>
export default {
  name: "ComponentX",
  props:
      {
        RootComponentPropsName: [String],
        RootComponentPropsAge: {
          type: Number,
          // required: true,
          // default: 18,
          validator(value) {
            return value > 0 && value < 40
          }
        },
        resetAgeCallbackFn: Function,
      },

  emits: ['age-reduce', 'age-reset'],
  computed: {
    ageDoubled() {
      return this.RootComponentPropsAge * 2
    }
  },
  methods: {
    onClickAgeReduce() {
      this.$emit(
          'age-reduce'
      )
    },
    onClickAgeReset() {
      this.$emit(
          'age-reset', 0
      )
    },

  }
}
</script>
