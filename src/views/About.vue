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
            Show modal size large
          </va-button>
          <va-modal v-model="showModalSizeLarge" :message="message">
            <va-card color="background" style="padding: 0.75rem;">
              <div class="row">
                <div class="flex md6">
                  <div class="item">Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry's standard dummy text ever since the 1500s, when an unknown printer took a galley of type and scrambled it to make a type specimen book. It has survived not only five centuries, but also the leap into electronic typesetting, remaining essentially unchanged. It was popularised in the 1960s with the release of Letraset sheets containing Lorem Ipsum passages, and more recently with desktop publishing software like Aldus PageMaker including versions of Lorem Ipsum.</div>
                </div>
                <div class="flex md6">
                  <div class="item">Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry's standard dummy text ever since the 1500s, when an unknown printer took a galley of type and scrambled it to make a type specimen book. It has survived not only five centuries, but also the leap into electronic typesetting, remaining essentially unchanged. It was popularised in the 1960s with the release of Letraset sheets containing Lorem Ipsum passages, and more recently with desktop publishing software like Aldus PageMaker including versions of Lorem Ipsum.</div>
                </div>
              </div>
            </va-card>
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
</style>
