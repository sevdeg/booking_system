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
          <va-modal v-model="showModalSizeLarge" :message="message">
            <!-- <va-card color="background" style="padding: 0.75rem;"> -->
              <div class="row">
                <div class="flex md4" id="leftDiv">
                  <va-card>
                    <va-card-content>Lorem ipsum dolor sit amet, consectetur adipiscing eli.</va-card-content>
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
                    <va-list>
                      <!-- Velg behandling list -->
                      <va-list-label>
                        Velg behandling
                      </va-list-label>
                      <va-list-item style="border: 0.5px solid;"
                        v-for="(contact, index) in contacts"
                        :key="index"
                      >
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
                  </div>
                </div>
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
export default {
  data () {
    return {
      contacts: [
        { name: 'Medisink Fotterapi' },
        { name: 'Rynkebehandling 1 område' },
        { name: 'Ansiktsbehandling hudpleie 60 min' },
        { name: 'Kjemisk peeling' }
      ],
      showModalSizeLarge: false
      // value1: 45
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
  background-color:lightblue;
}
  @media only screen and (max-width: 770px) {
    #leftDiv {
        display: none;
    }
    /* .flex md6 {
    } */
}
</style>
