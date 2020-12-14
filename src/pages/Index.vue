<template>
  <q-page class="flex containerr" style="max-width: 1920px">
    <h2 class="text-teal-4 large-screen-only" style="padding-left: 20%">
      QUER GANHAR CYBERPUNK 2077?
    </h2>
    <div class="absolute-center text-h2 text-teal-4 large-screen-only" style="padding-top: 300px" id="demo"></div>
    <div class="absolute-center text-h5 text-red-5 small-screen-only" style="padding-top: 250px" id="demo1"></div>
    <h4 class="text-dark text-bold small-screen-only" style="padding-left: 10%">
      QUER GANHAR CYBERPUNK 2077?
    </h4>
    <br />
    <div class="q-gutter-y-md absolute-center column" style="width: 320px">
      <form class="contact-form" @submit.prevent="sendEmail">

        <q-input
          ref="name"
          filled
          name="user_name"
          type="text"
          bg-color="yellow"
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
          bg-color="yellow"
          label="Email *"
          lazy-rules
          standout
          :rules="[(val) => (val && val.length > 0) || 'Escreva o Email']"
        >
          <template v-slot:prepend>
            <q-icon name="mail" />
          </template>
        </q-input>
   <q-btn label="Enviar" type="submit" color="teal-5" @click="seamless = true"/>
      </form>
        <q-dialog v-model="seamless" seamless position="bottom">
      <q-card class="bg-teal-5" style="width: 350px">
        <q-card-section class="row items-center no-wrap">
          <div>
            <div class="textt text-bold text-h5">Tudo certo?</div>
            <div class="text-yellow text-h7">Podemos lhe registrar no sorteio?</div>
          </div>

          <q-space />

          <q-btn fab round icon="done_outline" class="text-yellow" color="black" to="/Thx" />
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
      emailjs.sendForm('service_hj1he6p', 'template_g6f5gi9', e.target, 'user_F2eJn3d0x4QIDRMUqqymD')
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
      accept: true,
      seamless: false
    };
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
  background-image: url("https://db4sgowjqfwig.cloudfront.net/campaigns/205381/assets/990904/unnamed.gif?1564032863");
  background-position: 55%;
  background-size: 170vh;
  font-family: "Audiowide", cursive;
}

.textt {
  font-family: "Audiowide", cursive;
}
</style>
