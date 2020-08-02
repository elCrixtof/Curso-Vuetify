<template>
  <v-container>
    <v-row row wrap>
      <v-col xs="12" sm="6">
        <v-card>
          <v-img class="white--text align-end" height="400px" src="https://cdn.vuetifyjs.com/images/cards/docks.jpg">
            <v-card-title >Top 10 Australian beaches</v-card-title>
          </v-img>
          <v-card-title>
            <h2>Lorem, ipsum dolor.</h2>
          </v-card-title>
          <v-card-text>
            Lorem ipsum dolor sit amet consectetur adipisicing elit. Velit recusandae ratione accusantium voluptas enim, molestiae dolorem odit deserunt dolores quod!
          </v-card-text>
          <v-card-actions>
            <v-btn color="info" outlined>
              Accion
            </v-btn>
          </v-card-actions>
        </v-card>
      </v-col>

      <v-col xs="12" sm="6">
        <v-card>
          <v-img class="white--text align-end" height="400px" src="https://cdn.vuetifyjs.com/images/cards/docks.jpg">
            <v-card-title >Top 10 Australian beaches</v-card-title>
          </v-img>
          <v-card-title>
            <h2>Lorem, ipsum dolor.</h2>
          </v-card-title>
          <v-card-text>
            Lorem ipsum dolor sit amet consectetur adipisicing elit. Velit recusandae ratione accusantium voluptas enim, molestiae dolorem odit deserunt dolores quod!
          </v-card-text>
          <v-card-actions>
            <v-btn color="info"  outlined @click="dialog = true">
              Accion
            </v-btn>
          </v-card-actions>
        </v-card>
      </v-col>
    </v-row>

    <!-- Dialog -->
    <v-dialog v-model="dialog" persistent width="500px">
      <v-card>
        <v-card-title>
          Este es el titulo
        </v-card-title>
        <v-card-text>
          Lorem ipsum dolor sit, amet consectetur adipisicing elit. Soluta natus dignissimos dicta laboriosam, asperiores architecto obcaecati! Sed, libero excepturi voluptatibus consequatur explicabo, doloremque optio quisquam distinctio earum non, a vero.
        </v-card-text>
        <v-divider></v-divider>
        <v-card-actions>
          <v-btn @click="dialog = false">
            Cerrar
          </v-btn>
        </v-card-actions>
      </v-card>
    </v-dialog>

    <!-- fin dialog -->


  </v-container>
</template>

<script>
export default {
  data() {
    return {
      dialog: false,
    }
  },
}
</script>
