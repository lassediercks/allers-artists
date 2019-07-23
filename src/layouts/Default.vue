<template>
  <div class="layout">
    <header class="header">
      <g-link class="logo" to="/">
        <Logo :alt="$static.metaData.siteName"></Logo>
      </g-link>
    </header>
    <slot />
  </div>
</template>

<script>
import Logo from "../components/Logo.vue";

export default {
  components: { Logo },
  metaInfo: {
    link: [
      {
        href:
          "https://fonts.googleapis.com/css?family=Abril+Fatface&display=swap",
        rel: "stylesheet"
      },
      {
        href: "https://use.typekit.net/ozp3msn.css",
        rel: "stylesheet"
      },
      {
        href: "https://fonts.googleapis.com/css?family=Rock+Salt&display=swap",
        rel: "stylesheet"
      }
    ]
  }
};
</script>

<static-query>
query {
  metaData {
    siteName
  }
}
</static-query>

<style>
* {
  box-sizing: border-box;
}
:root {
}
html {
  font-size: 20px;
}
body {
  font-family: proxima-nova, sans-serif;
  margin: 0;
  padding: 0;
  line-height: 1.5;
}
.logo {
  font-family: "Abril Fatface", cursive;
  text-decoration: none;
  color: black;
  font-size: 30px;
  margin: 0;
  display: inline-block;
}

.layout {
  max-width: 760px;
  margin: 0 auto;
}

.header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 1em 1.5em 5em;
}

.nav__link {
  margin-left: 20px;
}
</style>
