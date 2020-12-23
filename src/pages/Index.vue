<template>
  <q-page class=" containerr" style="max-width: 1920px">
    <h2 class="text-teal-4 large-screen-only text-center q-pa-xl">
     RESGATE O SEU PRÊMIO 
    </h2>
    <h5 class="text-dark text-bold text-center q-pa-xl small-screen-only" >
     RESGATE O SEU PRÊMIO 
    </h5>
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
         <q-toggle class="text-black text-h6" v-model="accept" label="Habilito a Elements entrar em contato" />
   <q-btn label="Enviar" type="submit" color="white text-black" @click="seamless = true"/>
      </form>
        <q-dialog v-model="seamless" seamless position="bottom">
      <q-card class="bg-teal-5" style="width: 350px">
        <q-card-section class="row items-center no-wrap">
          <div>
            <div class="textt text-bold text-h5">Tudo certo?</div>
            <div class="text-yellow text-h7">Clique pra receber seu HQ</div>
          </div>

          <q-space />
          <form target="_blank" action="https://drive.google.com/file/d/1aCc49bOMDwdvAxwnfmk0fodnUsqCc1Jk/view?usp=sharing">
          <q-btn fab round icon="done_outline" class="text-yellow" color="black" to="https://drive.google.com/file/d/1aCc49bOMDwdvAxwnfmk0fodnUsqCc1Jk/view?usp=sharing" />
          </form>
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
  },
   methods: {
    onSubmit () {
      this.$refs.name.validate()
      this.$refs.age.validate()

      if (this.$refs.name.hasError || this.$refs.age.hasError) {
        this.formHasError = true
      }
      else if (this.accept !== true) {
        this.$q.notify({
          color: 'negative',
          message: 'Voce não quer nossas mensagens ? -_-'
        })
      }
      else {
        this.$q.notify({
          icon: 'done',
          color: 'positive',
          message: 'Foi...'
        })
      }
    },

    onReset () {
      this.name = null
      this.age = null

      this.$refs.name.resetValidation()
      this.$refs.age.resetValidation()
    }
  }
}
  var countDownDate = new Date("Dec 11, 2020 12:00:00").getTime();

// Update the count down every 1 second
  var x = setInterval(function() {

  // Get today's date and time
  var now = new Date().getTime();

  // Find the distance between now and the count down date
  var distance = countDownDate - now;

  // Time calculations for days, hours, minutes and seconds
  var days = Math.floor(distance / (1000 * 60 * 60 * 24));
  var hours = Math.floor((distance % (1000 * 60 * 60 * 24)) / (1000 * 60 * 60));
  var minutes = Math.floor((distance % (1000 * 60 * 60)) / (1000 * 60));
  var seconds = Math.floor((distance % (1000 * 60)) / 1000);

  // Display the result in the element with id="demo"
  document.getElementById("demo").innerHTML = days + "d " + hours + "h "
  + minutes + "m " + seconds + "s ";
   document.getElementById("demo1").innerHTML = days + "d " + hours + "h "
  + minutes + "m " + seconds + "s ";

  // If the count down is finished, write some text
  if (distance < 0) {
    clearInterval(x);
    document.getElementById("demo").innerHTML = "EXPIRED";
    document.getElementById("demo1").innerHTML = "EXPIRED";
  }
}, 1000);
</script>

<style scoped>
@import url("https://fonts.googleapis.com/css2?family=Audiowide&display=swap");
.containerr {
  background-image: url("https://desafio.elementsgaming.com.br/wp-content/uploads/2020/07/egdesafio1-scaled.jpg");
  background-size: 200vh;
  font-family: "Audiowide", cursive;
}

.textt {
  font-family: "Audiowide", cursive;
}
</style>
