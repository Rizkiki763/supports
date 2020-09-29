<template>
  <v-parallax
    src="@/components/Image/gambar6.png"
    dark
    height="600"
  >
  <v-card
    class="mx-auto mt-5"
    max-width="500"
    color="yellow lighten-3"

  >
    <v-card-title class="text-center justify-center py-6">
      <span>{{ currentTitle }}</span>
      <v-avatar
        color="primary lighten-2"
        class="subheading white--text"
        size="24"
        v-text="step"
      ></v-avatar>
    </v-card-title>

    <v-window v-model="step">
      <v-window-item :value="1">
        <v-card-text>
          <v-text-field
            label="Email"
            value=""
            filled
          ></v-text-field>
          <span class="caption grey--text text--darken-1">
            This is the email you will use to login to your Admin account
          </span>
        </v-card-text>
      </v-window-item>

      <v-window-item :value="2">
        <v-card-text>
          <v-text-field
            label="Password"
            type="password"
            filled
          ></v-text-field>
          <span class="caption grey--text text--darken-1">
            Please enter a password for your account
          </span>
        </v-card-text>
      </v-window-item>

      <v-window-item :value="3">
        <div class="pa-4 text-center">
          <v-img
            class="mb-4"
            contain
            height="128"
            src="@/components/Image/logosts.png"
          ></v-img>
          <h3 class="title font-weight-light mb-2">Welcome to Admin account</h3>
          <span class="caption grey--text">Welcome!</span>
        </div>
      </v-window-item>
    </v-window>

    <v-divider></v-divider>

    <v-card-actions>
      <v-btn
        :disabled="step === 1"
        text
        @click="step--"
      >
        Back
      </v-btn>
      <v-spacer></v-spacer>
      <v-btn
        :disabled="step === 3"
        color="primary"
        depressed
        @click="step++"
      >
        Next
      </v-btn>
    </v-card-actions>
  </v-card>
</v-parallax>
</template>


<script>
  export default {
    data: () => ({
      step: 1,
    }),

    computed: {
      currentTitle () {
        switch (this.step) {
          case 1: return 'Login'
          case 2: return 'Password'
          default: return 'Admin Account'
        }
      },
    },
  }
</script>