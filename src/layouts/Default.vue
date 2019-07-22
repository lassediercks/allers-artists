<template>
  <div class="layout">
    <header class="header">
      <g-link class="logo" to="/">{{ $static.metaData.siteName }}</g-link>
    </header>
    <slot />
  </div>
</template>

<script>
export default {
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
  --artist-name-font: "Rock Salt", cursive;
}
body {
  font-family: "Now", -apple-system, system-ui, BlinkMacSystemFont, "Segoe UI",
    Roboto, "Helvetica Neue", Arial, sans-serif;
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
  padding-left: 20px;
  padding-right: 20px;
}

.header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin-bottom: 20px;
  height: 80px;
}

.nav__link {
  margin-left: 20px;
}
</style>
