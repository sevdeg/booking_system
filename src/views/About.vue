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
            <!-- <div class="row">
                <div class="col-xs-12 col-md-3">.col-xs-12 .col-md-3

                </div>
                <div class="col-xs-12 col-md-3">.col-xs-12 .col-md-3

                </div>
                <div class="col-xs-12 col-md-3">.col-xs-12 .col-md-3

                </div>
                <div class="col-xs-12 col-md-3">.col-xs-12 .col-md-3

                </div>
            </div> -->
             <div class="row">
                <div class="flex md6 lg4">
                <va-card color="primary" gradient>
                    <va-card-title>Title</va-card-title>
                    <va-card-content>Lorem ipsum dolor sit amet, consectetur adipiscing elitLorem ipsum dolor sit amet, consectetur adipiscing elitLorem ipsum dolor sit amet, consectetur adipiscing elitLorem ipsum dolor sit amet, consectetur adipiscing elitLorem ipsum dolor sit amet, consectetur adipiscing elitLorem ipsum dolor sit amet, consectetur adipiscing elitLorem ipsum dolor sit amet, consectetur adipiscing elitLorem ipsum dolor sit amet, consectetur adipiscing elitLorem ipsum dolor sit amet, consectetur adipiscing elitLorem ipsum dolor sit amet, consectetur adipiscing elitLorem ipsum dolor sit amet, consectetur adipiscing elit.</va-card-content>
                </va-card>
                </div>
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
