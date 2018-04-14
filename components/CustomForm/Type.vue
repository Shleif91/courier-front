<template>
  <v-container>
    <v-layout row>
      <v-flex xs12>
        <v-radio-group v-model="type">
          <v-radio
            v-for="item in types"
            :key="item.title"
            :label="item.title"
            :value="item.title"
          ></v-radio>
        </v-radio-group>
      </v-flex>
    </v-layout>
  </v-container>
</template>

<script>
  export default {
    data () {
      return {
        type: 'Input',
        types: [
          {title: 'Input'},
          {title: 'Select'},
          {title: 'Checkbox'},
          {title: 'Radiobutton'},
          {title: 'Button'}
        ]
      }
    }
  }
</script>