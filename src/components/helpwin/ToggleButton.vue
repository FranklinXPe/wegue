<template>

  <v-dialog v-model="show" max-width="300" :hide-overlay="false">

    <v-btn icon slot="activator" dark>
      <v-icon medium>{{icon}}</v-icon>
      {{text}}
    </v-btn>

    <wgu-helpwin
      ref="helpwin"
      :icon="icon"
      :title="text"
      :headline="headline"
      :content="content"
      :infoLink="infoLink"
      :infoLinkText="infoLinkText"
      v-on:winxclose="show=false"
    />

  </v-dialog>

</template>

<script>

import HelpWin from './HelpWin'

export default {
  name: 'wgu-helpwin-btn',
  components: {
    'wgu-helpwin': HelpWin
  },
  props: {
    icon: {type: String, required: false, default: 'help'},
    text: {type: String, required: false},
    headline: {type: String, required: false},
    content: {type: String, required: false},
    infoLink: {type: String, required: false},
    infoLinkText: {type: String, required: false}
  },
  data: function () {
    return {
      show: false
    }
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style>

</style>
