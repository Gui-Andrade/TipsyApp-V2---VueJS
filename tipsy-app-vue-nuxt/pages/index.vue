<template>
  <v-card class="mx-auto mx-lg-auto" width="300px">
    <v-form
      ref="form"
      v-model="valid"
      lazy-validation
    >
      <v-card-text>
        <v-text-field
          v-model="total"
          label="Total"
          required
        ></v-text-field>

        <v-text-field
          v-model="tip"
          label="Tip"
          required
        ></v-text-field>

        <v-text-field
          v-model="peopleSharing"
          label="PeopleSharing"
          required
        ></v-text-field>
      </v-card-text>

      <v-card-actions class="pa-md-4">
        <v-btn
          outlined
          color="success"
          @click="calculateTip"
        >
          Calculate
        </v-btn>
        <v-spacer></v-spacer>
        <v-btn
          outlined
          color="warning"
          @click="reset"
        >
          Reset Form
        </v-btn>
      </v-card-actions>
    </v-form>
  </v-card>
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
        const total = parseInt(this.total)
        const tip = parseInt(this.tip)
        const peopleSharing = parseInt(this.peopleSharing)
        const sharedTip = (total + tip) / peopleSharing
        alert(sharedTip)
      }
    },
  }
</script>
