<template>
  <v-row justify="center">
    <v-dialog v-model="dialog" persistent max-width="400">
      <template v-slot:activator="{on}">
        <v-btn color="pink" v-on="on" dark>Peringatan</v-btn>
      </template>
      <v-card>
        <v-card-title class="headline">Warning!</v-card-title>
        <v-card-text>
          <v-form>
            <v-text-field label="Name" v-model="title" prepend-icon="mdi-folder-account"></v-text-field>
              <!-- date picker -->
              <!-- <v-menu
                v-model="menu2"
                :close-on-content-click="false"
                :nudge-right="40"
                transition="scale-transition"
                offset-y
                min-width="290px"
              >
                <template v-slot:activator="{ on }">
                  <v-text-field
                    v-model="date"
                    label="Date"
                    prepend-icon="mdi-calendar"
                    readonly
                    v-on="on"
                  ></v-text-field>
                </template>
                <v-date-picker color="pink" v-model="date" @input="menu2 = false"></v-date-picker>
              </v-menu> -->

            
            <v-menu>
              <template v-slot:activator="{on}">
                <v-text-field :value="formattedDate" label="Input Date" v-on="on" prepend-icon="mdi-calendar"></v-text-field>
              </template>
              <v-date-picker v-model="date"></v-date-picker>
            </v-menu>
            
            <v-textarea label="Information" v-model="content" prepend-icon="mdi-information"></v-textarea>
          </v-form>
        </v-card-text>
        <v-card-actions>
          <v-spacer></v-spacer>
          <v-btn color="green" text @click="dialog = false">Agree</v-btn>
          <v-btn color="red" text @click="dialog = false">DisAgree</v-btn>
        </v-card-actions>
      </v-card>
    </v-dialog>
  </v-row>
</template>

<script>
// import format from "date-fns/format"
import moment from "moment"

export default {
  data() {
    return {
      dialog: false,
      title: "",
      content: "",
      date: new Date().toISOString().substr(0, 10),
      menu2: "false",
    };
  },
  methods: {
    // submit(){
    //   console.log(this.title, this.content)
    // }
  },
  computed: {
    formattedDate(){
      return this.date ? moment(this.date).format("dddd, Do MMMM YYYY") : ""
    }
  }
};
</script>

<style scoped>
</style>