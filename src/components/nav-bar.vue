<template>
  <b-navbar type="info" variant="primary" toggleable>
    <b-navbar-toggle target="nav_collapse"></b-navbar-toggle>
    <b-navbar-brand href="#">
        <b-img src="src/assets/logo.svg" fluid alt="KarboMarket" />
      <div>arboMarket</div>
    </b-navbar-brand>
    <b-collapse is-nav id="nav_collapse">
      <b-navbar-nav class="ml-auto">
        <b-nav-item href="#">Somethings</b-nav-item>
        <b-nav-item href="http://karbowanec.com/">karbowanec.com</b-nav-item>
        <b-nav-item href="https://github.com">GitHub</b-nav-item>
      </b-navbar-nav>
    </b-collapse>
  </b-navbar>
</template>

<script>

export default {
  name: 'NavBar',
  data () {
    return {}
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style>
.navbar-nav>li>a {
    color: #fff;
    text-transform: uppercase;
}

.navbar-nav>li>a:hover,
.navbar-nav>li>a:focus {
    color: #fff;
    text-decoration: none;
    outline: 0;
}

input {
    border-radius: 0!important;
}

hr {
    display: block;
    height: 1px;
    border: 0;
    border-top: 1px solid rgb(110, 110, 110);
    margin: 1em 0;
    padding: 0;
}

.navbar {
    font-weight: 800;
    font-size: 18px;
    padding-top: 15px;
    padding-bottom: 15px;
    background: #0c84e4;
    /* For browsers that do not support gradients */
    background: -webkit-linear-gradient(#0c84e4, #cee6f9);
    /* For Safari 5.1 to 6.0 */
    background: -o-linear-gradient(#0c84e4, #cee6f9);
    /* For Opera 11.1 to 12.0 */
    background: -moz-linear-gradient(#0c84e4, #cee6f9);
    /* For Firefox 3.6 to 15 */
    background: linear-gradient(#0c84e4, #cee6f9);
    border: none;
    border-radius: 0;
}

.navbar .icon-bar {
    background: #fff;
}

.navbar .navbar-nav>li>a:hover {
    background-color: #0c84e4;
}

.navbar-brand>div {
    color: #fff;
    position: absolute;
    margin-top: -40px;
    margin-left: 55px;
}
</style>
