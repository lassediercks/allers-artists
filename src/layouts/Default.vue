<template>
  <div class="layout">
    <link
      href="https://fonts.googleapis.com/css?family=Abril+Fatface&display=swap"
      rel="stylesheet"
    />
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
body {
  font-family: -apple-system, system-ui, BlinkMacSystemFont, "Segoe UI", Roboto,
    "Helvetica Neue", Arial, sans-serif;
  margin: 0;
  padding: 0;
  line-height: 1.5;
}
.logo {
  font-family: "Abril Fatface", cursive;
  text-decoration: none;
  color: black;
  font-size: 30px;
  margin: 0 auto;
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
