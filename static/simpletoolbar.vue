<!--
Copyright 2020 Google LLC

Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at

    https://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.
-->
<template>
  <b-navbar type='is-info'>
    <template slot="brand">
      <b-navbar-item style="font-size:24px" @click="goBackToMainPage">
        <i class="fa fa-arrow-left"></i>&nbsp;{{toolbarBrand}}
      </b-navbar-item>
    </template>
    <template slot="end">
      <b-navbar-item @click="openFeedbackForm">
        <i class="fa fa-comment fa-fw"></i>&nbsp;Feedback
      </b-navbar-item>
    </template>
  </b-navbar>
</template>

<script>
  import * as Util from './Util.js';
  import { mapGetters } from "vuex";

  export default {
    data() {
      return {toolbarBrand: window.location.host};
    },
    computed: {
      ...mapGetters(['version'])
    },
    methods: {
      goBackToMainPage() {
        this.$router.push(`/${Util.getNonEnglishLocale(this.$i18n.locale)}`);
      },
      openFeedbackForm() {
        const url = Util.getFeedbackFormUrl(navigator.userAgent, this.version);
        window.open(url, '_new');
      }
    }
  }
</script>
