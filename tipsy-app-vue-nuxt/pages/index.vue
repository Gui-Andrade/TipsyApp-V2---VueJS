<template>
  <v-form
    ref="form"
    v-model="valid"
    lazy-validation
  >
    <v-text-field
      v-model="total"
      :rules="totalRules"
      label="Total"
      required
    ></v-text-field>

    <v-text-field
      v-model="tip"
      :rules="tipRules"
      label="Tip"
      required
    ></v-text-field>

    <v-text-field
      v-model="people"
      :rules="peopleRules"
      label="People"
      required
    ></v-text-field>

    <v-btn
      color="success"
      class="mr-4"
      @click="calculateTip"
    >
      Calculate
    </v-btn>

    <v-btn
      color="warning"
      class="mr-4"
      @click="reset"
    >
      Reset Form
    </v-btn>

  </v-form>
</template>

<script>
export default {
    data: () => ({
      valid: true,
      total: '',
      tip: '',
      peopleSharing: '',
      select: null,
      checkbox: false,
    }),

    methods: {
      reset () {
        this.$refs.form.reset()
      },
      calculateTip () {
        alert('vai')
      }
    },
  }
</script>
