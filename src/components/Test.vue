<!--<template>
  <div class="container">
    <article>
      <header>
        <div class="progress">
          <div class="progress-step"
          :class="{'active':index === activeStep}"
          v-for="(step, index) in formSteps"
          :key="'step'+index">
            {{ index + 1 }}
          </div>
        </div>
      </header>
      <section :class="animation">
        <h2>{{ formSteps[activeStep].title }}</h2>
        <div class="input-fields">
          <div class="input-container"
          v-for="(field, contact, index) in formSteps[activeStep].fields"
          :key="'field'+index">
            <input type="checkbox" :class="{'wrong-input': !field.valid}" v-model="field.value"  style="margin-left:260px;" required>
            <label class="input-label">{{ field.label }}</label>
          </div>
        </div>
        <div class="actions">
          <button v-if="activeStep +1 < formSteps.length -1" @click="checkFields">next</button>
          <button v-if="activeStep +1 === formSteps.length -1" @click="checkFields">done</button>
        </div>
      </section>
    </article>
  </div>
</template>

<script>
export default {
  data: () => {
    return {
      activeStep: 0,
      animation: 'animate-in',
      contacts: [
        { name: 'Audrey Clay', address: '644 Vermont Court, Freelandville, Kentucky, 2619', img: 'https://randomuser.me/api/portraits/women/5.jpg' },
        { name: 'Aguirre Klein', address: '626 Carroll Street, Roulette, Ohio, 1477', img: 'https://randomuser.me/api/portraits/men/1.jpg' },
        { name: 'Tucker Kaufman', address: '887 Winthrop Street, Tryon, Florida, 3912', img: 'https://randomuser.me/api/portraits/men/3.jpg' },
        { name: 'Herbert Keller', address: '286 NW. Shore St.Longwood, FL 32779', img: 'https://randomuser.me/api/portraits/men/5.jpg' }
      ],
      formSteps: [
        {
          title: 'Velg behandling',
          fields: [
            { label: 'Medisink Fotterapi', value: '', valid: true, pattern: /.+/ },
            { label: 'Rynkebehandling 1 område', value: '', valid: true, pattern: /.+/ },
            { label: 'Ansiktsbehandling hudpleie 60 min', value: '', valid: true, pattern: /.+/ },
            { label: 'Kjemisk peeling', value: '', valid: true, pattern: /.+/ }
          ]
        },
        {
          title: 'Velg klient',
          fields: [
            { label: 'What does CSS stand for?', value: '', valid: true, pattern: /.+/ },
            { label: 'HTML tag for an internal style sheet?', value: '', valid: true, pattern: /.+/ },
            { label: 'Property for the background color?', value: '', valid: true, pattern: /.+/ }
          ]
        },
        {
          title: 'Your data',
          fields: [
            { label: 'Your first name?', value: '', valid: true, pattern: /.+/ },
            { label: 'Your last name?', value: '', valid: true, pattern: /.+/ },
            { label: 'Your email?', value: '', valid: true, pattern: /^[^\s@]+@[^\s@]+\.[^\s@]+$/ }
          ]
        },
        {
          title: 'Thank you for participating!'
        }
      ]
    }
  },
  methods: {
    nextStep () {
      this.animation = 'animate-out'
      setTimeout(() => {
        this.animation = 'animate-in'
        this.activeStep += 1
      }, 550)
    },
    checkFields () {
      let valid = true
      this.formSteps[this.activeStep].fields.forEach(field => {
        if (!field.pattern.test(field.value)) {
          valid = false
          field.valid = false
        } else {
          field.valid = true
        }
      })
      if (valid) {
        this.nextStep()
      } else {
        this.animation = 'animate-wrong'
        setTimeout(() => {
          this.animation = ''
        }, 400)
      }
    }
  }
}
</script>

<style lang="scss" scoped>
  @mixin flexbox() {
    display: flex;
    justify-content: center;
    align-items: center;
  }
  .container {
    @include flexbox();
    width: 100%;
    min-height: 100vh;
    font-family: 'Noto Sans', sans-serif;
    background: radial-gradient(blue, #A43227);
  }
  article {
    display: flex;
    margin: 10px;
    width: calc(100% - 20px);
    max-width: 720px;
    min-height: 480px;
    perspective: 1000px;
    header {
      @include flexbox();
      width: 60px;
      height: 480px;
      background-color: #fff;
      border-right: 2px dotted blue;
      box-shadow: 0 15px 30px rgba(0,0,0,.2),
                  0 10px 10px rgba(0,0,0,.2);
    }
    .progress-step {
      @include flexbox();
      position: relative;
      width: 30px;
      height: 30px;
      border-radius: 50%;
      margin-bottom: 20px;
      color: #fff;
      background-color: blue;
      font-weight: bold;
      &.active {
        background-color: blue;
        ~ .progress-step {
          color: #555;
          background-color: #ccc;
        }
        ~ .progress-step::before {
          background-color: #ccc;
        }
      }
      &:before {
        content: '';
        position: absolute;
        top: -20px;
        width: 2px;
        height: 20px;
        background-color: blue;
        z-index: 10;
      }
      &:first-child::before {
        display: none;
      }
    }
    section {
      @include flexbox();
      flex-direction: column;
      width: 100%;
      background-color: #fff;
      box-shadow: 0 15px 30px rgba(0,0,0,.2),
                  0 10px 10px rgba(0,0,0,.2);
      h2 {
        font-size: 1.6rem;
        color:blue;
        margin: 0;
        padding: 20px;
      }
      .input-fields {
        @include flexbox();
        flex-direction: column;
        width: 100%;
      }
      .input-container {
        position: relative;
        padding: 30px 20px 20px 20px;
        width: calc(100% - 40px);
        max-width: 400px;
        input {
          position: relative;
          width: 100%;
          font-family: 'Noto Sans', sans-serif;
          font-size: 1.35rem;
          outline: none;
          background: transparent;
          box-shadow: none;
          border: none;
          border-bottom: 2px dashed blue;
          &:valid + .input-label {
            top: 10px;
            left: 20px;
            font-size: .7rem;
            font-weight: normal;
            color: #999;
          }
          &.wrong-input + .input-label {
            color: #B92938;
          }
        }
      }
      .input-label {
        position: absolute;
        top: 32px;
        left: 20px;
        font-size: 1.35rem;
        pointer-events: none;
        transition: .2s ease-in-out;
      }
      .actions {
        margin: 0;
        button {
          color: #fff;
          background-color: blue;
          font-size: 1.35rem;
          padding: 5px 20px;
          margin: 0;
          text-transform: uppercase;
          border-radius: 3px;
          cursor: pointer;
        }
      }
    }
  }
</style>
-->
<template>
  <!--<div class="about">
    <h1>This is an about page</h1>
  </div>-->
  <html>
    <head>
        <title>Example</title>
    </head>
    <body>
        <header>
        </header>
          <main>
          <va-button class="mr-2 mb-2" @click="showModalSizeLarge = !showModalSizeLarge">
            Book Time!
          </va-button>
          <va-button class="mr-2 mb-2" @click="showModalSizeLargeer">
            Show modal size large
          </va-button>
          <va-modal v-model="showModalSizeLarge" :message="message">
            <!-- <va-card color="background" style="padding: 0.75rem;"> -->
              <div class="row">
                <div class="flex md4" id="leftDiv">
                  <va-card>
                    <!-- <va-card-title>Velg behandling, fortell litt type info du vil vise</va-card-title> -->
                    <va-card-content>Lorem ipsum dolor sit amet, consectetur adipiscing elit.</va-card-content>
                    <va-card-content>Lorem ipsum dolor sit amet, consectetur adipiscing elit.</va-card-content>
                    <va-card-content>Lorem ipsum dolor sit amet, consectetur adipiscing elit.</va-card-content>
                    <va-card-content>Lorem ipsum dolor sit amet, consectetur adipiscing elit.</va-card-content>
                    <va-card-content>Lorem ipsum dolor sit amet, consectetur adipiscing elit.</va-card-content>
                    <va-card-content>Lorem ipsum dolor sit amet, consectetur adipiscing elit.</va-card-content>
                  </va-card>
                  <!-- <div class="item">ventre divvvvLorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry's standard dummy text ever since the 1500s, when an unknown printer took a galley of type and scrambled it to make a type specimen book. It has survived not only five centuries, but also the leap into electronic typesetting, remaining essentially unchanged. It was popularised in the 1960s with the release of Letraset sheets containing Lorem Ipsum passages, and more recently with desktop publishing software like Aldus PageMaker including versions of Lorem Ipsum.</div> -->
                </div>
                <!-- Velg behandling div -->
                <div class="flex md8">
                  <div class="item">
                    <!-- LIST DESCRIPTION -->
                    <!-- v-for="type in behandlingstyper" :key="type.id" -->
                    <va-list>
                      <va-list-label>
                        Velg Klient
                      </va-list-label>
                       <va-list>

    <va-list-item
      v-for="(contact, index) in contacts"
      :key="index"
    >
      <va-list-item-section avatar>
        <va-avatar>
          <img :src="contact.img">
        </va-avatar>
      </va-list-item-section>

      <va-list-item-section>
        <va-list-item-label>
          {{ contact.name }}
        </va-list-item-label>

        <va-list-item-label caption>
          {{ contact.address }}
        </va-list-item-label>
      </va-list-item-section>

      <va-list-item-section icon>
        <va-icon
          name="remove_red_eye"
          color="gray"
        />
      </va-list-item-section>
    </va-list-item>
  </va-list>
                      <va-list-item
                        v-for="(Behandlingstype, index) in behandlingstyper" @click="getId(Behandlingstype.navn)" style="display:block"
                        :key="index"
                      >

                        <va-list-item-section>
                          <va-list-item-label>
                            {{ Behandlingstype.navn }}
                          </va-list-item-label>

                          <va-list-item-label caption :lines="index + 1">
                            {{ Behandlingstype.beskrivelse }}
                          </va-list-item-label>
                        </va-list-item-section>
                        <!-- mulighet for å sette inn icon senere
                          <va-list-item-section icon>
                          <va-icon
                            name="remove_red_eye"
                            color="gray"
                          />
                        </va-list-item-section> -->
                      </va-list-item>
                    </va-list>
                  </div>
                </div>
                <form @submit.prevent="addMessage">
                  <select v-model="role">
                    <option value="developer">web developer</option>
                    <option value="designer">web designer</option>
                  </select>
                  <button>Order</button>
                </form>
                <p>status: {{ role }}</p>
                <!-- <p>handler om klikk: {{ getId(Behandlingstype.navn) }}</p> -->
              </div>
            <!-- </va-card> -->
          </va-modal>
        </main>
        <footer>
        </footer>
    </body>
</html>
</template>
<script>
import { projectFirestore } from '../main'
export default {
  data () {
    return {
      showModalSizeLarge: false,
      behandlingstyper: [],
      role: null,
      getNavn: null,
      contacts: [
        { name: 'Audrey Clay', address: '644 Vermont Court, Freelandville, Kentucky, 2619', img: 'https://randomuser.me/api/portraits/women/5.jpg' },
        { name: 'Aguirre Klein', address: '626 Carroll Street, Roulette, Ohio, 1477', img: 'https://randomuser.me/api/portraits/men/1.jpg' },
        { name: 'Tucker Kaufman', address: '887 Winthrop Street, Tryon, Florida, 3912', img: 'https://randomuser.me/api/portraits/men/3.jpg' },
        { name: 'Herbert Keller', address: '286 NW. Shore St.Longwood, FL 32779', img: 'https://randomuser.me/api/portraits/men/5.jpg' }
      ]
    }
  },
  // Legg til alle de i array med unshift, så bare skriv ut det i en kvittering
  // du får ut nå verdien til onclick, neste steg blir vel å gjøre display none og display block, sjekk sevde sin kode
  methods: {
    getId (typeNavn) {
      console.log('klikket på get ID')
      console.log(typeNavn)
      this.role = typeNavn
      console.log(this.role)
    },
    showModalSizeLargeer () {
      console.log('kliker på modal')
      this.fetchBehandlingstyper()
    },
    vaList () {
      console.log('clicked on va-list')
    },
    handleSubmit () {
      console.log('trykket på submit')
      console.log(this.role)
      this.addMessage()
    },
    handlerNavn () {
      console.log('klikket på en av items')
      console.log(this.getNavn)
    },
    addMessage () {
      console.log('inne i add message')
      if (this.role) {
        this.feedback = null
        projectFirestore.collection('ordre').add({
          role: this.role
          // to: this.$route.params.id,
          // from: this.authUser.email,
          // description: this.message,
          // createdAt: new Date(),
        }).then(() => {
          this.role = null
        })
      } else {
        console.log('feil')
      }
    },
    fetchBehandlingstyper () {
      console.log('inne i behandlingstyper')
      projectFirestore.collection('behandlingstyper').get().then(behandlingstyper => {
        behandlingstyper.docs.forEach(doc => {
          console.log('data')
          console.log(doc.data().id)
          const type = doc.data()
          console.log(type)
          type.id = doc.id //  Iden over mot autogenerert id
          console.log('id')
          console.log(type.id)
          this.behandlingstyper.push(type)
        })
        console.log('alle behandlingstyper:', this.behandlingstyper)
      })
    }
  }
}
</script>
<style scoped>
  .item {
    border: 1px solid rgb(212, 205, 205);
    background-color: #ffffff;
    text-align: center;
  }

  .va-list-item:hover {
  background-color: lightblue;
}
  @media only screen and (max-width: 770px) {
    #leftDiv {
        display: none;
    }
    /* .flex md6 {
    } */
}
</style>
