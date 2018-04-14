<template>
  <v-container>
    <v-layout row>
      <v-flex xs-12>
        <v-btn fab dark color="indigo" @click.native="isStepperVisible = true" v-if="!isStepperVisible">
          <v-icon dark>add</v-icon>
        </v-btn>
        <v-stepper v-model="e1" v-if="isStepperVisible">
          <v-stepper-header>
            <v-stepper-step step="1" :complete="e1 > 1">Select type</v-stepper-step>
            <v-divider></v-divider>
            <v-stepper-step step="2" :complete="e1 > 2">Select component</v-stepper-step>
            <v-divider></v-divider>
            <v-stepper-step step="3">View</v-stepper-step>
          </v-stepper-header>
          <v-stepper-items>
            <v-stepper-content step="1">
              <type></type>
              <v-btn color="primary" @click.native="e1 = 2">Continue</v-btn>
              <v-btn flat @click.native="clearForm">Cancel</v-btn>
            </v-stepper-content>
            <v-stepper-content step="2">
              <v-card color="grey lighten-1" class="mb-5" height="200px"></v-card>
              <v-btn color="primary" @click.native="e1 = 3">Continue</v-btn>
              <v-btn flat @click.native="clearForm">Cancel</v-btn>
            </v-stepper-content>
            <v-stepper-content step="3">
              <v-card color="grey lighten-1" class="mb-5" height="200px"></v-card>
              <v-btn color="primary" @click.native="clearForm">Finish</v-btn>
              <v-btn flat @click.native="clearForm">Cancel</v-btn>
            </v-stepper-content>
          </v-stepper-items>
        </v-stepper>
      </v-flex>
    </v-layout>
  </v-container>
</template>

<script>
  import Type from '@/components/CustomForm/Type'

  export default {
    components: {
      Type
    },
    data () {
      return {
        e1: 0,
        isStepperVisible: false
      }
    },
    methods: {
      clearForm () {
        this.e1 = 0
        this.isStepperVisible = false
      }
    }
  }
</script>