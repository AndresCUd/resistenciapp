<template>
  <v-dialog v-model="showDialog" width="300px">
    <v-card class="p-1">
      <v-col cols="6" offset="3" style="padding:0;padding-top:10px">
        <img
          src="@/components/Icon.png"
          alt="App icon"
          width="150px"
          style="align:right"
        />
      </v-col>
      <v-col>
        <v-card-text class="black--text">
          Bienvenido a ResistenciApp! <br /><br />
          La única app del #ParoNacional. <br /><br />
          <b
            >Toda tu información es privada, nunca te pediremos ningún dato
            personal.</b
          >
          <br />
          <br />
          Únicamente necesitamos tu ubicación para generar un mapa en tiempo
          real con el estado de las protestas en la ciudad.<br /><br />
          Somos una iniciativa independiente, sin ánimo de lucro y sin fines
          políticos.
          <br />
          <br />
          Somos una herramienta informativa para los protestantes.
        </v-card-text>
      </v-col>
      <v-card-actions>
        <v-col>
          <v-btn @click="$emit('accept')" large color="primary">ACEPTO</v-btn>
          <v-btn :to="{ name: 'nothing' }" color="error" large>NO ACEPTO</v-btn>
        </v-col>
      </v-card-actions>
    </v-card>
  </v-dialog>
</template>

<script>
export default {
  props: {
    value: {
      type: Boolean,
      required: true
    }
  },
  computed: {
    showDialog: {
      get() {
        return this.value
      },
      set(value) {
        this.$emit('input', value)
      }
    }
  }
}
</script>

<style lang="scss" scoped></style>
