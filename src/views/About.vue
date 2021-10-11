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
          <p>
          <va-button class="mr-2 mb-2" @click="showModalSizeLarge = !showModalSizeLarge">
            Show modal size large
          </va-button>
          <va-modal v-model="showModalSizeLarge" :message="message">
            <div style="height: 13rem; border: 2px solid var(--va-primary); width:600px;">
            <va-sidebar textColor="dark">
              <va-sidebar-item>
                <va-sidebar-item-content>
                  <va-icon name="dashboard"/>
                  <!-- User can hide item with css if he wants -->
                  <va-sidebar-item-title> Velg behandling </va-sidebar-item-title>
                </va-sidebar-item-content>
              </va-sidebar-item>
              <va-sidebar-item>
                <va-sidebar-item-content>
                  <va-icon name="room" />
                  <va-sidebar-item-title> Velg klient </va-sidebar-item-title>
                </va-sidebar-item-content>
              </va-sidebar-item>
               <va-sidebar-item>
                <va-sidebar-item-content>
                <va-icon name="dashboard"/>
                  <!-- User can hide item with css if he wants -->
                  <va-sidebar-item-title> Velg Dato og kl </va-sidebar-item-title>
                </va-sidebar-item-content>
              </va-sidebar-item>
              <va-sidebar-item>
                <va-sidebar-item-content>
                <va-icon name="dashboard"/>
                  <!-- User can hide item with css if he wants -->
                  <va-sidebar-item-title> Skriv informasjon! </va-sidebar-item-title>
                </va-sidebar-item-content>
              </va-sidebar-item>
              <va-sidebar-item>
                <va-sidebar-item-content>
                <va-icon name="dashboard"/>
                  <!-- User can hide item with css if he wants -->
                  <va-sidebar-item-title> Bekreft </va-sidebar-item-title>
                </va-sidebar-item-content>
              </va-sidebar-item>
            </va-sidebar>
          </div>
          </va-modal>
          </p>
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
      showModalSizeLarge: false
    }
  }
}

</script>
