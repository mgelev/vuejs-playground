<template>
<v-parallax
    dark
    src="https://cdn.vuetifyjs.com/images/backgrounds/vbanner.jpg"
  >
    <v-row
      align="center"
      justify="center"
    >
      <v-col class="text-center" cols="12">
 

   <h1 dark>Select Country</h1>
        <v-overflow-btn
          class="my-2"
          :items="countries"
          label="Select Country..."
          editable
          item-value="text"
        ></v-overflow-btn>

        <h1>Select Height Range</h1>
       
       
      <v-row>
        <v-col class="px-4">
          <v-range-slider
            color="black"
            v-model="range"
            :max="max"
            :min="min"
            hide-details
            class="align-center"
          >
            <template v-slot:prepend>
              <v-text-field
                v-model="range[0]"
                class="mt-0 pt-0"
                hide-details
                single-line
                type="number"
                style="width: 60px"
              ></v-text-field>
            </template>
            <template v-slot:append>
              <v-text-field
                v-model="range[1]"
                class="mt-0 pt-0"
                hide-details
                single-line
                type="number"
                style="width: 60px"
              ></v-text-field>
            </template>
          </v-range-slider>
        </v-col>
      </v-row>

     From:  {{this.range[0]}}

     To: {{this.range[1]}}




      <v-simple-table dark>
    <template v-slot:default>
      <thead>
        <tr>
          <th class="text-left">Name</th>
          <th class="text-left">Height</th>
        </tr>
      </thead>
      <tbody>
        <tr v-for="item in desserts" :key="item.name">
          <td>{{ item.name }}</td>
          <td>{{ item.calories }}</td>
        </tr>
      </tbody>
    </template>
  </v-simple-table>
      </v-col>

    </v-row>

 </v-parallax>
    
</template>

<script>
// @ is an alias to /src

export default {
 
       data () {
        return {
            slider: 40,
            range: [0, 6000],

             min: 0,
             max: 6000,

            countries: ['bg','en','gb','as','fa','fwf','fweweef'],
        }
    },
    // 
   
  
}
</script>




