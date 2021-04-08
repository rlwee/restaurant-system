<template>
  <div id="nav">
    <header>
      <div class="container-fluid header-container">
        <div class="row justify-content-center header-row-container">
          <div class="col-lg-10 header-column-container">
            <ul class="ul-header">
              <li><router-link to="/about"> About </router-link></li>
              <li><router-link to="/products"> Products </router-link></li>
              <li><router-link to="/"> Freddie Angular </router-link></li>
              <li>Reservation</li>
              <li>Contact Us</li>
            </ul>
          </div>
        </div>
      </div>
    </header>

    <router-view />
  </div>
</template>

<style>
#app {
  font-family: Roboto, sans-serif, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
}

#nav {
}

.routerlink {
  color: black;
}

.router-link-active {
  color: black !important;
}

#nav a {
  font-weight: bold;
  color: #2c3e50;
}

#nav a.router-link-exact-active {
  color: #42b983;
}

header {
  box-shadow: 0px 0px 9px 3px rgba(41, 41, 41, 0.25);
}

.header-container {
}

.header-row-container {
}

.header-column-container {
  /* border: 2px solid black; */
  padding-top: 15px;
  padding-bottom: 15px;
}

.ul-header {
  list-style-type: none;
  display: flex;
  margin-bottom: 0;
}

li {
  margin: auto;
  font-size: 14px;
}

li:nth-child(1),
li:nth-child(2),
li:nth-child(4),
li:nth-child(5) {
  position: relative;
  top: 2px;
}

.ul-header > li:nth-child(3) {
  font-family: "Pacifico", cursive;
  font-size: 35px;
}
</style>
