<template>
  <div>
    <!-- <v-layout row>
      <v-flex xs12 md6>
        <v-card dark tile flat color="deep-purple lighten-3">
          <v-card-text>Lorem ipsum dolor sit amet consectetur adipisicing elit.Lorem ipsum dolor sit amet consectetur adipisicing eliLorem ipsum dolor sit amet consectetur adipisicing eli consectetur adipisicing eliLorem ipsum dolor sit amet consectetur </v-card-text>
        </v-card>
      </v-flex>
      
      <v-flex xs4 md2>
        <v-card dark tile flat color="deep-purple lighten-1">
          <v-card-text>Lorem ipsum dolor sit amet consectetur adipisicing elit.</v-card-text>
        </v-card>
      </v-flex>

      <v-flex xs4 md2>
        <v-card dark tile flat color="deep-purple darken-2">
          <v-card-text>orem ipsum dolor sit amet consectetur adipisicing elit.</v-card-text>
        </v-card>
      </v-flex>

      <v-flex xs4 md2>
        <v-card dark tile flat color="deep-purple darken-1">
          <v-card-text>orem ipsum dolor sit amet consectetur adipisicing elit.</v-card-text>
        </v-card>
      </v-flex>
    </v-layout>

    <v-layout row>
      <v-flex md3>
        <v-card dark tile flat color="red lighten-2">
          <v-card-text>orem ipsum dolor sit amet .</v-card-text>
        </v-card>
      </v-flex> 

      <v-flex md3>
        <v-card dark tile flat color="red lighten-3">
          <v-card-text>Lorem ipsum dolor sit amet.</v-card-text>
        </v-card>
      </v-flex>

      <v-flex md3>
        <v-card dark tile flat color="red lighten-1">
          <v-card-text>Lorem ipsum dolor sit amet.</v-card-text>
        </v-card>
      </v-flex>

      <v-flex md3>
        <v-card dark tile flat color="red darken-3">
          <v-card-text>Lorem ipsum dolor sit amet.</v-card-text>
        </v-card>
      </v-flex>
    </v-layout>-->

    <!-- <v-row v-for="n in 2" :key="n" :class="n === 1 ? '' : ''" no-gutters>
      <v-col v-for="k in n + 1" :key="k">
        <v-card class="pa-2" outlined tile>{{ k }} of {{ n + 1 }}</v-card>
      </v-col>
    </v-row> -->

    <v-row no-gutters>
      <v-col sm="12" md="6" >
        <v-card class="pa-2" outlined tile>Lorem ipsum dolor sit amet consectetur adipisicing elit. Culpa maxime deserunt nulla eius inventore, quasi tempora,.</v-card>
        <p class="px-4">Lorem ipsum dolor sit amet consectetur adipisicing elit. Amet quod, eveniet deleniti, ipsam aliquid omnis officiis autem soluta quaerat sapiente dolorem aperiam labore? At, corrupti fugiat perspiciatis ratione suscipit voluptate.</p>
      </v-col>
      <v-col sm="12" md="6">
        <v-card class="pl-2" flat tile>Lorem ipsum dolor sit amet consectetur adipisicing elit. Aliquid quidem totam iste rem aliquam esse voluptate accusantium.</v-card>
        <p class="px-4">Lorem ipsum dolor sit amet consectetur adipisicing elit. Corporis nesciunt eius modi quam non vel assumenda velit sapiente? Vel ea dolor minima odio quasi laudantium expedita tenetur quidem magni adipisci?</p>
      </v-col>
    </v-row>
    <v-row no-gutters>
      <v-col md="4" sm="6">
        <v-card class="pa-2" color="red lighten-2" outlined tile>1</v-card>
      </v-col>
      <v-col md="4" sm="6">
        <v-card class="pa-2" color="red lighten-1" outlined tile>2</v-card>
      </v-col>
      <v-col md="4" sm="12">
        <v-card class="pa-2" color="red lighten-3" outlined tile>3</v-card>
      </v-col>
    </v-row>
  </div>
</template>

<script>
export default {
  data() {
    return {};
  }
};
</script>
