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
  <div>
		<h1>Page Not Found</h1>
		<p>The page does not exist on the server.</p>
		<h2>Why am I seeing this?</h2>
		<p>Perhaps you came from an outdated link on another website, or the file was deleted, or you may have mistyped the address.</p>
		<h2>What now?</h2>
		<p>Click the cat below. It will cheer her up, and you will be taken back to the main page.</p>
    <router-link to="/" class="logo">
      <img src="/images/404_cat.png">
    </router-link>
  </div>
</template>

<script>
  import '../images/404_cat.png';

  export default {
    mounted() {
      document.title = 'Page not found';
      const m = document.createElement('meta');
      m.name = 'robots'; 
      m.content = 'noindex'; 
      document.head.appendChild(m);
    }
  }
</script>

<style scoped>
  div {
    margin: 0 auto;
    max-width: 616px;
    padding: 8px 16px;
    font-family: 'Roboto', 'Helvetica Neue', sans-serif;
    font-size: 16px;
    line-height: 24px;
    background-color: rgb(47, 95, 157);
    color: rgb(255, 255, 255);
  }
  h1, h2, h3 {
    font-family: 'Roboto', 'Helvetica Neue', sans-serif;
    font-weight: 300;
    color: rgb(255, 255, 255);
  }
  h1 {
    margin: 24px 0 16px 0;
    padding: 0 0 16px 0;
    border-bottom: 1px solid rgb(255, 255, 255);
    font-size: 32px;
    line-height: 36px;
  }
  h2 {
    margin: 24px 0 16px 0;
    padding: 0;
    font-size: 20px;
    line-height: 32px;
    color: rgb(255, 255, 255);
  }
  p {
    margin: 0;
    margin-bottom: 16px;
  }
  .logo {
    display: block;
    text-align: center;
    margin-top: 48px;
    margin-bottom: 24px;
  }
  @media screen and (max-width: 616px) {
    body {
      margin-top: 24px;
    }
    .logo  {
      margin: 0;
    }
  }
</style>
