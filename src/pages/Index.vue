<template>
  <q-page class=" containerr flex" style="max-width: 2560">
    <h1 class="text-dark large-screen-only text-center " style="padding-left: 15%">
     RESGATE O SEU PRÊMIO 
    </h1>
    <h4 class="text-dark text-bold text-center q-pa-md small-screen-only" >
     RESGATE O SEU PRÊMIO 
    </h4>
    <div class="q-gutter-y-md absolute-center column" style="width: 320px">
      <form class="contact-form text-purple" @submit.prevent="sendEmail">

        <q-input
          ref="name"
          filled
          name="user_name"
          type="text"
          bg-color="grey text-dark"
          v-model="name"
          label="Nome *"
          lazy-rules
          standout
          :rules="[(val) => (val && val.length > 0) || 'Escreva o Nome']"
        >
          <template v-slot:prepend>
            <q-icon name="account_circle" />
          </template>
        </q-input>
        <q-input
          filled
          v-model="email"
          type="email"
          name="user_email"
          bg-color="grey text-dark"
          label="Email *"
          lazy-rules
          standout
          :rules="[(val) => (val && val.length > 0) || 'Escreva o Email']"
        >
          <template v-slot:prepend>
            <q-icon name="mail" />
          </template>
        </q-input>
    <hr>
         <q-toggle class="text-grey-4 text-h6" v-model="accept" label="Habilito a Elements entrar em contato" />
<hr>
   <q-btn label="Enviar" type="submit" color="white text-black" @click="seamless = true"/>
      </form>
        <q-dialog v-model="seamless" seamless position="bottom">
      <q-card class="bg-grey-5" style="width: 350px">
        <q-card-section class="row items-center no-wrap">
          <div>
            <div class="textt text-bold text-h5">Tudo certo?</div>
            <div class="text-brown textt text-h7">Clique pra receber seu HQ</div>
          </div>
          <q-space />
          <q-btn fab round icon="done_outline" class="text-brown" color="black" to="/Thx" />
        </q-card-section>
      </q-card>
    </q-dialog>
  </div>
  </q-page>
</template>

<script>
import emailjs from 'emailjs-com';
export default {
   methods: {
    sendEmail: (e) => {
      emailjs.sendForm('service_ak32cfk', 'template_s61d9cq', e.target, 'user_WsYwkDH83qgP2HaxA9BrP')
        .then((result) => {
            console.log('SUCCESS!', result.status, result.text);
        }, (error) => {
            console.log('FAILED...', error);
        });
    }
  },
  name: "PageIndex",
  data() {
    return {
      icon: false,
      card: false,
      dense: false,
      name: null,
      email: null,
      accept: false,
      seamless: false
    };
  }
}
</script>

<style scoped>
@import url("https://fonts.googleapis.com/css2?family=Audiowide&display=swap");
.containerr {
  background-image: url("https://desafio.elementsgaming.com.br/wp-content/uploads/2020/07/egdesafio1-scaled.jpg");
  background-size: 250vh;
  font-family: "Audiowide", cursive;
}

.textt {
  font-family: "Audiowide", cursive;
}
</style>
