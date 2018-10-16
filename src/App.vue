<template>
  <div id="app">
    <nav>
      <div>
        <h1>LotWCS</h1>
        <div>
          <router-link to="/">Archetypes</router-link>
          <router-link to="/about">Styles</router-link>
          <router-link to="/about">Skills</router-link>
          <router-link to="/about">Characteristics</router-link>
        </div>
      </div>
      <router-link to="/about">Full Sheet</router-link>
    </nav>
    <router-view/>
  </div>
</template>

<style lang="scss">
nav {
  display: flex;
  justify-content: space-between;
  align-items: center;
  border-bottom: 1px solid black;
  padding: 10px 10px 0 10px;

  div {
    display: flex;
    align-items: center;

    h1 {
      font-size: 28px;
      margin: 0;
      margin-right: 50px;
      font-weight: 300;
    }
  }

  a {
    border: 1px solid black;
    border-bottom: 0;
    padding: 12px;
    margin: 0;
    font-size: 20px;
    text-decoration: none;
    color: black;

    -webkit-border-top-left-radius: 7px;
    -webkit-border-top-right-radius: 7px;
    -moz-border-radius-topleft: 7px;
    -moz-border-radius-topright: 7px;
    border-top-left-radius: 7px;
    border-top-right-radius: 7px;
  }
}

#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
</style>
