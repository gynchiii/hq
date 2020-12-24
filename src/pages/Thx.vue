<template>
  <div class="fullscreen textt containerr text-white text-center q-pa-md flex flex-center">
   <particles-bg type="lines" :bg="true" />
    <div>
      <div class="text-purple-7 large-screen-only" style="font-size: 15vh">
        O SÁBIO SABE QUE NÃO SABE.
      </div>
      <div class="small-screen-only text-purple-7" style="font-size: 7vh">
        O SÁBIO SABE QUE NÃO SABE.
      </div>
      <div class="large-screen-only text-h2 text-white" style="opacity:.4">
       É apenas o começo...
      </div>
      <div class="text-h4 text-white small-screen-only" style="opacity:.4">
       É apenas o começo...
      </div>
    </div>
    <h5 class="q-pa-xl text-purple-7 large-screen-only">leia no celular apontando sua câmera aqui ></h5>
    <q-img src="https://desafio.elementsgaming.com.br/wp-content/uploads/2020/12/HQ.png" class="large-screen-only"  style="width: 26vh"></q-img>
    <q-dialog class="textt" v-model="card">
      <q-card class="textt bg-black">
        <q-btn color="purple-7" fab icon="close" v-close-popup />
        <q-timeline class="bg-black q-pa-md" :layout="layout" color="purple">
          <q-timeline-entry class="text-purple-6 q-pa-md" heading>
            SEU HQ ESTÁ PRONTO, MAS... VOCÊ NÃO QUER MAIS?...
          </q-timeline-entry>

          <q-timeline-entry
            title="agora que você colocou Nome/email. Clique abaixo para download de seu HQ"
            subtitle="OLha só..."
            class="text-purple-7"
            side="right"
            icon="done"
          >
               <form
                action="https://mega.nz/folder/zyIjHAwa#jWRs7A3ZsJCfCTqdlWHunQ"
                target="_blank"
              >
                <q-btn
                  round
                  color="purple-7"
                  type="submit"
                  class="text-black"
                  icon="cloud_download"
                />
              </form>
              <br>
            <div class="text-h6 text-purple-7">
            !!!! E TEM MAIS !!!! Nos seguindo no Instagram, você ganha o direito de pedir a edição 2 dos HQ's na DM !! O que você tá esperando ? corre lá, é só clicar aqui embaixo
            </div>
              <br>
             <form
                action="https://www.instagram.com/elements.gaming/?"
                target="_blank"
              >
                <q-btn
                  round
                  color="purple-7"
                  type="submit"
                  rounded
                  class="text-black"
                  icon="alternate_email"
                />
              </form>
          </q-timeline-entry>

          <q-timeline-entry
            title="Muito bem jovem"
            subtitle="Você é um ótimo gamer"
            side="left"
            class="text-purple-6"
          >
            <div class="text-purple-7">
              Fique ligado no nosso insta, pois iremos fazer muita coisas juntos ainda.
            </div>
          </q-timeline-entry>

          <q-timeline-entry
            title="Elements Gaming"
            subtitle="Bora Ganhar"
            side="left"
            color="black"
            icon="done_all"
          >
          </q-timeline-entry>
        </q-timeline>
      </q-card>
    </q-dialog>
    </div>
  </div>
</template>

<script>
import { ParticlesBg } from "particles-bg-vue";
export default {
  name: 'Thx',
  components: {
    ParticlesBg
  },
   data() {
    return {
      icon: false,
      card: true,
      seamless: false
    }
  },
  computed: {
        layout() {
          return this.$q.screen.lt.sm
            ? "dense"
            : this.$q.screen.lt.md
            ? "comfortable"
            : "loose";
         }
    }
}
</script>

<style scoped>
@import url("https://fonts.googleapis.com/css2?family=Audiowide&display=swap");
.containerr {
  font-family: "Audiowide", cursive;
}
.textt {
  font-family: "Audiowide", cursive;
}
</style>