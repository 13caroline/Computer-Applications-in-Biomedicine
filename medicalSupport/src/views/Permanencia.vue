<template>
  <div id="login">
    <v-card color="#34b2b7" flat height="100px" tile>
      <v-toolbar extended extension-height="100" color="#34b2b7" dark>
        <v-toolbar-title class="font-weight-light"
          >Serviço de Urgência</v-toolbar-title
        >

        <v-spacer></v-spacer>
        <v-btn icon to="/menu">
          <v-icon>home</v-icon>
        </v-btn>
        <v-btn text @click="terminar()" class="text-capitalize">
          <v-icon class="mr-2">logout</v-icon> Terminar Sessão
        </v-btn>
      </v-toolbar>
    </v-card>

    <v-card class="mx-auto" width="1300">
      <v-row>
        <v-col >
          <v-row no-gutters>
            <v-card class="mt-4 ml-4" height="250" width="500" outlined>
              <v-img
                class = "mt-2 ml-2"
                src="@/assets/Tempo de Permanencia por Patologia.jpg"
                aspect-ratio="2.1"
                cover
              ></v-img>
            </v-card>
            <v-card class="mt-4 ml-4" height="250" width="420" outlined>
              <v-img
                src="@/assets/Tempo de Internamento associado à Idade.jpg"
                aspect-ratio="1.7"
                contain
              ></v-img>
            </v-card>
          </v-row>
          <v-row no-gutters>
            <v-card class="mt-4 ml-4" height="380" width="940" outlined>
              <v-img
                class = "mt-8 ml-2"
                src="@/assets/Tempo de Permanencia por Prioridade.png"
                aspect-ratio="2.7"
                contain
              ></v-img>
            </v-card>
          </v-row>
        </v-col>
        <v-col cols="3">
          <v-card class="mt-4 mr-6 ml-0" outlined>
            <v-card-title>Informações Relacionadas</v-card-title>
            <v-row v-for="(btn, index) in buttons" :key="index">
              <v-btn
                class="ml-2 text-decoration-underline text-capitalize"
                color="#34b2b7"
                :to="btn.to"
                text
                >{{ btn.title }}</v-btn
              >
            </v-row>
          </v-card>
        </v-col>
      </v-row>
    </v-card>
    <v-card flat height = "100" color = "transparent"></v-card>
    <Footer/>
  </div>
</template>

<script>
import Footer from '@/components/Footer.vue'
export default {
  name: "login",
  data() {
    return {
      buttons: [
        { title: "Qualidade de Dados", to: "/qualidadedados" },
        { title: "Intervenções e Exames", to: "/qualidade/dados/intervencoes&exames" },
        { title: "Tempos de Espera", to: "/qualidade/dados/espera" },
      ],
    };
  },
  components: {
    Footer
  },
  methods: {
    terminar: function () {
      this.$router.push("/");
    },
  },
};
</script>

<style scoped>
#login {
  width: 100%;
  min-height: 100%;
  position: absolute;
  top: 0;
  left: 0;
  background-color: #f5f5f5;
  background-size: cover;
}
</style>