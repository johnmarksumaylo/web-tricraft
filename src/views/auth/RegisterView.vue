<script setup>
import { ref } from 'vue'

const theme = ref('light')

function onClick() {
  theme.value = theme.value === 'light' ? 'dark' : 'light'
}
</script>

<template>
  <v-responsive class="border rounded">
    <v-app :theme="theme">
      <v-app-bar class="px-3" color="green-darken-2">
        <v-spacer></v-spacer>

        <v-btn
          :prepend-icon="theme === 'light' ? 'mdi-weather-sunny' : 'mdi-weather-night'"
          variant="elevated"
          slim
          @click="onClick"
        ></v-btn>
      </v-app-bar>

      <v-main>
        <v-container>
          <v-row>
            <v-col cols="12" md="6"> </v-col>
          </v-row>
          <v-card
            color="green-darken-2"
            class="mx-auto mt-16"
            prepend-icon="mdi-wrench"
            subtitle="We find ways!"
            width="400"
            elevation="20"
          >
            <template v-slot:title>
              <span class="font-weight-black">Tri - Craft</span>
            </template>

            <v-card-text class="bg-surface-light pt-4">
              <v-form fast-fail @submit.prevent>
                <v-row>
                  <v-col cols="6">
                    <v-text-field label="First Name"></v-text-field>
                  </v-col>
                  <v-col cols="6"><v-text-field label="Last Name"></v-text-field></v-col>
                </v-row>

                <v-text-field label="E-mail"></v-text-field>

                <v-row>
                  <v-col cols="6"
                    ><v-text-field label="Password" type="password"></v-text-field
                  ></v-col>
                  <v-col cols="6"
                    ><v-text-field label="Confirm Password" type="password"></v-text-field
                  ></v-col>
                </v-row>

                <v-btn class="mt-2" type="submit" block>Register</v-btn>
              </v-form>

              <v-divider class="my-5"></v-divider>
              <h4 class="text-center">
                Already have acount?
                <RouterLink class="text-success" to="/login">Click here to Login</RouterLink>
              </h4>
            </v-card-text>
          </v-card>
        </v-container>
      </v-main>

      <v-footer class="font-weight-bold" color="green-darken-2" border app
        >2024 - Tricraft | All Rights Reserved</v-footer
      >
    </v-app>
  </v-responsive>
</template>
