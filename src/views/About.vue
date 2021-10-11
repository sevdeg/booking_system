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
          <va-button @click="showModal = !showModal">
            Book Time
          </va-button>
          <va-modal v-model="showModal" :message="message" title="Overview" >
            <div style="height: 13rem; border: 2px solid var(--va-primary);">
            <va-sidebar textColor="dark">
              <va-sidebar-item>
                <va-sidebar-item-content>
                  <va-icon name="dashboard" />
                  <!-- User can hide item with css if he wants -->
                  <va-sidebar-item-title> Dashboard </va-sidebar-item-title>
                </va-sidebar-item-content>
              </va-sidebar-item>

              <va-sidebar-item active>
                <va-sidebar-item-content>
                  <va-icon name="room" />
                  <va-sidebar-item-title> Sidebar demo </va-sidebar-item-title>
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
      showModal: false
    }
  }
}

</script>
