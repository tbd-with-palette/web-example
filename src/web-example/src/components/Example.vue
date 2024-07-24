<template>
  <v-container class="fill-height">
    <v-responsive
      class="align-centerfill-height mx-auto"
      max-width="900"
    >
      <v-img
        class="mb-4"
        height="150"
        src="@/assets/logo.png"
      />

      <div class="text-center">
        <div class="text-body-2 font-weight-light mb-n1">Trunk Based Development</div>

        <h1 class="text-h2 font-weight-bold">Spectro Cloud Palette</h1>
        <RouterLink to="HelloWorld">Go to Hello World</RouterLink><br/>
        <strong>Current route path:</strong> {{ $route.fullPath }}<br>
        <h2>{{ currentAnswer }}</h2>
        <v-button @click="getAnswer"> Press Me Now </v-button>

      </div>
    </v-responsive>
  </v-container>
</template>

<script>
import axios from 'axios'

export default {
  data: function () {
    return {
      currentAnswer: "None",
    }
  },
  methods: {
    getAnswer() {
      axios
        .get('http://code-dev.local/api/foo/bar?bang')
        .then(response => (this.currentAnswer = response))
    }
  }
}

</script>

