<template>
  <div>
    <v-row no-gutters>
      <v-col cols="12">
        <v-menu v-model="menu1" :close-on-content-click="false" max-width="290">
          <template v-slot:activator="{ on }">
            <v-text-field
              :value="computedDateFormattedMomentjs"
              clearable
              label="Formatted with Moment.js"
              readonly
              v-on="on"
              @click:clear="date = null"
            ></v-text-field>
          </template>
          <v-date-picker :first-day-of-week="0" locale="id" color="pink lighten-1" v-model="date" @change="menu1 = false"></v-date-picker>
        </v-menu>
      </v-col>
    </v-row>
  </div>
</template>

<script>
import moment from "moment";
import ("moment/locale/id")
export default {
  data() {
    return {
      date: new Date().toISOString().substr(0, 10),
      menu2: false,
      menu1: false
    };
  },
  computed: {
    computedDateFormattedMomentjs () {
        return this.date ? moment(this.date).format('DD MMMM YYYY') : ''
    },
  }
};
</script>

<style scoped>
</style>