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
            <div class="row">
                <div class="flex md6" id="leftDiv">
                  <div class="item1"> <div style="height: 21rem; border: 0.5px solid var(--va-primary);">
    <va-sidebar textColor="dark">
      <va-sidebar-item>
        <va-sidebar-item-content>
          <a href="#tekst1"><va-icon name="dashboard" /></a>
          <!-- User can hide item with css if he wants -->
          <va-sidebar-item-title> Velg behandling </va-sidebar-item-title>
        </va-sidebar-item-content>
      </va-sidebar-item>
       <va-sidebar-item>
        <va-sidebar-item-content>
          <va-icon name="dashboard" />
          <!-- User can hide item with css if he wants -->
          <va-sidebar-item-title> Velg klient </va-sidebar-item-title>
        </va-sidebar-item-content>
      </va-sidebar-item>
       <va-sidebar-item>
        <va-sidebar-item-content>
          <va-icon name="dashboard" />
          <!-- User can hide item with css if he wants -->
          <va-sidebar-item-title> Velg Dato og Klokkeslett </va-sidebar-item-title>
        </va-sidebar-item-content>
      </va-sidebar-item>
       <va-sidebar-item>
        <va-sidebar-item-content>
          <va-icon name="dashboard" />
          <!-- User can hide item with css if he wants -->
          <va-sidebar-item-title> Personlig informasjon </va-sidebar-item-title>
        </va-sidebar-item-content>
      </va-sidebar-item>
      <va-sidebar-item active>
        <va-sidebar-item-content>
          <va-icon name="dashboard" />
          <va-sidebar-item-title> Bekreft </va-sidebar-item-title>
        </va-sidebar-item-content>
      </va-sidebar-item>
    </va-sidebar>
  </div></div>
                </div>
                <div class="flex md6">
                  <div class="item2"><va-list>
                  <va-list-label>
                    Velg klient
                  </va-list-label>

                  <va-list-item v-for="(contact, index) in contacts" :key="index" to="/">
                    <va-list-item-section avatar>
                      <va-avatar >
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
                </va-list></div>
                </div>
              </div>
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
      showModalSizeLarge: false,
      contacts: [
        { name: 'Audrey Clay', address: '644 Vermont Court, Freelandville, Kentucky, 2619', img: 'https://randomuser.me/api/portraits/women/5.jpg' },
        { name: 'Aguirre Klein', address: '626 Carroll Street, Roulette, Ohio, 1477', img: 'https://randomuser.me/api/portraits/men/1.jpg' },
        { name: 'Tucker Kaufman', address: '887 Winthrop Street, Tryon, Florida, 3912', img: 'https://randomuser.me/api/portraits/men/3.jpg' },
        { name: 'Herbert Keller', address: '286 NW. Shore St.Longwood, FL 32779', img: 'https://randomuser.me/api/portraits/men/5.jpg' }
      ]
    }
  }
}

</script>
<style>
 .item1 {
    border: 1px solid rgb(212, 205, 205);
    background-color: #ffffff;
    text-align: center;
  }
  @media all and (max-width: 770px) {
  #leftDiv { display: none; }
}
.item2 {
    /* shows when targeted */
    border: 1px solid rgb(212, 205, 205);
}
.va-list-item:hover{
  background-color: red;
}

</style>
