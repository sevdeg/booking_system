<template>
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
