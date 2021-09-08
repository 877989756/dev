<template>
  <v-card flat color="#fdf4bf" height="730px">
    <drawers/>
    <Top/>
    <v-container >
      <v-row>
        <v-col offset="3" cols="6">
          <v-card
              class="pa-4" align="center">
            <Submit/>
            <v-card-text style="height: 10px;"></v-card-text>
          </v-card>
        </v-col>
      </v-row>
    </v-container>
  </v-card>
</template>
<script>
import Submit from "@/views/Submit";
import Top from "@/views/Top";
import Drawers from "@/views/drawers";
export default {
  components: {Drawers, Top, Submit}
}
</script>