<template>
  <div class="fullscreen textt containerr text-white text-center q-pa-md flex flex-center">
    <div>
      <div class="text-yellow-5 large-screen-only" style="font-size: 20vh">
        OBRIGADO POR PARTICIPAR.
      </div>
      <div class="small-screen-only text-yellow-5" style="font-size: 7vh">
        OBRIGADO POR PARTICIPAR.
      </div>
      <div class="large-screen-only text-h2 text-white" style="opacity:.4">
       Boa sorte...
      </div>
      <div class="text-h4 text-white small-screen-only" style="opacity:.4">
       Boa sorte...
      </div>
    </div>
    <q-dialog class="textt" v-model="card">
      <q-card class="textt bg-yellow-5">
        <q-btn color="teal-6" flat icon="close" v-close-popup />
        <q-timeline class="bg-yellow-5" :layout="layout" color="teal-5">
          <q-timeline-entry class="text-teal-6" heading>
            SE CHEGOU ATÉ AQUI...
          </q-timeline-entry>

          <q-timeline-entry
            title="agora que você colocou Nome/email."
            subtitle="Prossiga..."
            side="right"
            icon="done"
          >
          <br>
            <div class="text-h6">
             Vá até nossa page do instagram, e verifique se já está seguindo a gente. Clicando no botão abaixo
             <form
                action="https://www.instagram.com/elements.gaming/?"
                target="_blank"
              >
                <q-btn
                  round
                  color="teal-6"
                  type="submit"
                  icon="alternate_email"
                />
              </form>
            </div>
          </q-timeline-entry>

          <q-timeline-entry
            title="Nos Seguindo, agora..."
            subtitle="Boa sorte gamers"
            side="left"
          >
            <div>
              Curte o post do sorteio e siga as instruções na legenda do post, BORAAA...
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
export default {
  name: 'Thx',
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
  background-image: url("https://cdn.dribbble.com/users/546766/screenshots/5322841/untitled-4.gif");
  background-position: 50%;
  font-family: "Audiowide", cursive;
}
.textt {
  font-family: "Audiowide", cursive;
}
</style>