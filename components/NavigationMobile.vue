<template>
<nav class="navbar is-fixed-top">
  <div class="navbar-brand">
    <a aria-current="page" class="navbar-item" href="/">
      <h2 class="title is-5">Macguire Rintoul</h2>
    </a>
    <div v-on:click="toggleMobileMenu" class="navbar-burger burger" data-target="navMenu" aria-label="menu" aria-expanded="false">
      <span aria-hidden="true"></span>
      <span aria-hidden="true"></span>
      <span aria-hidden="true"></span>
    </div>
  </div>
  <div id="navMenu" :class="mobileMenuClass">
    <div class="navbar-end">
      <nuxt-link v-on:click.native="toggleMobileMenu" class="navbar-item" to="/">Home</nuxt-link>
      <nuxt-link v-on:click.native="toggleMobileMenu" class="navbar-item" to="/about">About</nuxt-link>
      <nuxt-link v-on:click.native="toggleMobileMenu" class="navbar-item" to="/styleguide">Style Guide</nuxt-link>
    </div>
  </div>
</nav>
</template>

<script>
export default {
  data: function() {
    return {
      showMobileMenu: false
    }
  },
  methods: {
    toggleMobileMenu: function() {
      console.log('Toggling mobile menu');
      this.showMobileMenu = !this.showMobileMenu;
    }
  },
  computed: {
    mobileMenuClass: function () {
      return 'navbar-menu ' + (this.showMobileMenu ? 'is-active' : '');
    }
  }
}
</script>

<style lang="scss" scoped>
// Navbar CSS from Bulma
// https://bulma.io/
@-webkit-keyframes spinAround-data-v-cb42bb9e {
from {
    -webkit-transform: rotate(0deg);
            transform: rotate(0deg);
}
to {
    -webkit-transform: rotate(359deg);
            transform: rotate(359deg);
}
}
@keyframes spinAround-data-v-cb42bb9e {
from {
    -webkit-transform: rotate(0deg);
            transform: rotate(0deg);
}
to {
    -webkit-transform: rotate(359deg);
            transform: rotate(359deg);
}
}
.is-unselectable {
  -webkit-touch-callout: none;
  -webkit-user-select: none;
  -moz-user-select: none;
  -ms-user-select: none;
  user-select: none;
}
.navbar-link:not(.is-arrowless)::after {
  border: 3px solid transparent;
  border-radius: 2px;
  border-right: 0;
  border-top: 0;
  content: " ";
  display: block;
  height: 0.625em;
  margin-top: -0.4375em;
  pointer-events: none;
  position: absolute;
  top: 50%;
  -webkit-transform: rotate(-45deg);
          transform: rotate(-45deg);
  -webkit-transform-origin: center;
          transform-origin: center;
  width: 0.625em;
}

/*! minireset.css v0.0.4 | MIT License | github.com/jgthms/minireset.css */
html,
body,
p,
ol,
ul,
li,
dl,
dt,
dd,
blockquote,
figure,
pre,
iframe,
hr,
h1,
h2,
h3,
h4,
h5,
h6 {
  margin: 0;
  padding: 0;
}
h1,
h2,
h3,
h4,
h5,
h6 {
  font-size: 100%;
  font-weight: normal;
}
ul {
  list-style: none;
}
*, *::before, *::after {
  box-sizing: inherit;
}
a {
  color: #3273dc;
  cursor: pointer;
  text-decoration: none;
}
a:hover {
    color: #363636;
}
span {
  font-style: inherit;
  font-weight: inherit;
}
.navbar {
  background-color: #FFF;
  min-height: 3.25rem;
  position: relative;
  z-index: 30;
}
.navbar > .container {
    align-items: stretch;
    display: flex;
    min-height: 3.25rem;
    width: 100%;
}
.navbar.is-fixed-bottom, .navbar.is-fixed-top {
    left: 0;
    position: fixed;
    right: 0;
    z-index: 30;
}
.navbar.is-fixed-top {
    top: 0;
}
.navbar-brand,
.navbar-tabs {
  align-items: stretch;
  display: flex;
  flex-shrink: 0;
  min-height: 3.25rem;
}
.navbar-brand a.navbar-item:hover {
  background-color: transparent;
}
.navbar-tabs {
  -webkit-overflow-scrolling: touch;
  max-width: 100vw;
  overflow-x: auto;
  overflow-y: hidden;
}
.navbar-burger {
  color: #4a4a4a;
  cursor: pointer;
  display: block;
  height: 3.25rem;
  position: relative;
  width: 3.25rem;
  margin-left: auto;
}
.navbar-burger span {
    background-color: currentColor;
    display: block;
    height: 1px;
    left: calc(50% - 8px);
    position: absolute;
    -webkit-transform-origin: center;
            transform-origin: center;
    transition-duration: 86ms;
    transition-property: background-color, opacity, -webkit-transform;
    transition-property: background-color, opacity, transform;
    transition-property: background-color, opacity, transform, -webkit-transform;
    transition-timing-function: ease-out;
    width: 16px;
}
.navbar-burger span:nth-child(1) {
      top: calc(50% - 6px);
}
.navbar-burger span:nth-child(2) {
      top: calc(50% - 1px);
}
.navbar-burger span:nth-child(3) {
      top: calc(50% + 4px);
}
.navbar-burger:hover {
    background-color: rgba(0, 0, 0, 0.05);
}
.navbar-burger.is-active span:nth-child(1) {
    -webkit-transform: translateY(5px) rotate(45deg);
            transform: translateY(5px) rotate(45deg);
}
.navbar-burger.is-active span:nth-child(2) {
    opacity: 0;
}
.navbar-burger.is-active span:nth-child(3) {
    -webkit-transform: translateY(-5px) rotate(-45deg);
            transform: translateY(-5px) rotate(-45deg);
}
.navbar-menu {
  display: none;
}
.navbar-item,
.navbar-link {
  color: #4a4a4a;
  display: block;
  line-height: 1.5;
  padding: 0.5rem 0.75rem;
  position: relative;
}
.navbar-item .icon:only-child,
  .navbar-link .icon:only-child {
    margin-left: -0.25rem;
    margin-right: -0.25rem;
}
a.navbar-item,
.navbar-link {
  cursor: pointer;
}
a.navbar-item:hover, a.navbar-item.is-active,
  .navbar-link:hover,
  .navbar-link.is-active {
    background-color: #fafafa;
    color: #3273dc;
}
.navbar-item {
  display: block;
  flex-grow: 0;
  flex-shrink: 0;
}
.navbar-item img {
    max-height: 1.75rem;
}
.navbar-item.has-dropdown {
    padding: 0;
}
.navbar-item.is-expanded {
    flex-grow: 1;
    flex-shrink: 1;
}
.navbar-item.is-tab {
    border-bottom: 1px solid transparent;
    min-height: 3.25rem;
    padding-bottom: calc(0.5rem - 1px);
}
.navbar-item.is-tab:hover {
      background-color: transparent;
      border-bottom-color: #3273dc;
}
.navbar-item.is-tab.is-active {
      background-color: transparent;
      border-bottom-color: #3273dc;
      border-bottom-style: solid;
      border-bottom-width: 3px;
      color: #3273dc;
      padding-bottom: calc(0.5rem - 3px);
}
.navbar-content {
  flex-grow: 1;
  flex-shrink: 1;
}
.navbar-link:not(.is-arrowless) {
  padding-right: 2.5em;
}
.navbar-link:not(.is-arrowless)::after {
    border-color: #3273dc;
    margin-top: -0.375em;
    right: 1.125em;
}
.navbar-dropdown {
  font-size: 0.875rem;
  padding-bottom: 0.5rem;
  padding-top: 0.5rem;
}
.navbar-dropdown .navbar-item {
    padding-left: 1.5rem;
    padding-right: 1.5rem;
}
.navbar-divider {
  background-color: whitesmoke;
  border: none;
  display: none;
  height: 2px;
  margin: 0.5rem 0;
}
@media screen and (max-width: 1087px) {
.navbar > .container {
    display: block;
}
.navbar-brand .navbar-item,
  .navbar-tabs .navbar-item {
    align-items: center;
    display: flex;
}
.navbar-link::after {
    display: none;
}
.navbar-menu {
    background-color: white;
    box-shadow: 0 8px 16px rgba(10, 10, 10, 0.1);
    padding: 0.5rem 0;
}
.navbar-menu.is-active {
      display: block;
}
.navbar.is-fixed-bottom-touch, .navbar.is-fixed-top-touch {
    left: 0;
    position: fixed;
    right: 0;
    z-index: 30;
}
.navbar.is-fixed-bottom-touch {
    bottom: 0;
}
.navbar.is-fixed-bottom-touch.has-shadow {
      box-shadow: 0 -2px 3px rgba(10, 10, 10, 0.1);
}
.navbar.is-fixed-top-touch {
    top: 0;
}
.navbar.is-fixed-top .navbar-menu, .navbar.is-fixed-top-touch .navbar-menu {
    -webkit-overflow-scrolling: touch;
    max-height: calc(100vh - 3.25rem);
    overflow: auto;
}
html.has-navbar-fixed-top-touch,
  body.has-navbar-fixed-top-touch {
    padding-top: 3.25rem;
}
html.has-navbar-fixed-bottom-touch,
  body.has-navbar-fixed-bottom-touch {
    padding-bottom: 3.25rem;
}
}
@media screen and (min-width: 1088px) {

.navbar {
    min-height: 3.25rem;
}
.navbar.is-spaced {
      padding: 1rem 2rem;
}
.navbar.is-spaced .navbar-start,
      .navbar.is-spaced .navbar-end {
        align-items: center;
}
.navbar.is-spaced a.navbar-item,
      .navbar.is-spaced .navbar-link {
        border-radius: 4px;
}
.navbar.is-transparent a.navbar-item:hover, .navbar.is-transparent a.navbar-item.is-active,
    .navbar.is-transparent .navbar-link:hover,
    .navbar.is-transparent .navbar-link.is-active {
      background-color: transparent !important;
}
.navbar.is-transparent .navbar-item.has-dropdown.is-active .navbar-link, .navbar.is-transparent .navbar-item.has-dropdown.is-hoverable:hover .navbar-link {
      background-color: transparent !important;
}
.navbar.is-transparent .navbar-dropdown a.navbar-item:hover {
      background-color: whitesmoke;
      color: #0a0a0a;
}
.navbar.is-transparent .navbar-dropdown a.navbar-item.is-active {
      background-color: whitesmoke;
      color: #3273dc;
}
.navbar-burger {
    display: none;
}
.navbar-item,
  .navbar-link {
    align-items: center;
    display: flex;
}
.navbar-item {
    display: flex;
}
.navbar-item.has-dropdown {
      align-items: stretch;
}
.navbar-item.has-dropdown-up .navbar-link::after {
      -webkit-transform: rotate(135deg) translate(0.25em, -0.25em);
              transform: rotate(135deg) translate(0.25em, -0.25em);
}
.navbar-item.has-dropdown-up .navbar-dropdown {
      border-bottom: 2px solid #dbdbdb;
      border-radius: 6px 6px 0 0;
      border-top: none;
      bottom: 100%;
      box-shadow: 0 -8px 8px rgba(10, 10, 10, 0.1);
      top: auto;
}
.navbar-item.is-active .navbar-dropdown, .navbar-item.is-hoverable:hover .navbar-dropdown {
      display: block;
}
.navbar.is-spaced .navbar-item.is-active .navbar-dropdown, .navbar-item.is-active .navbar-dropdown.is-boxed, .navbar.is-spaced .navbar-item.is-hoverable:hover .navbar-dropdown, .navbar-item.is-hoverable:hover .navbar-dropdown.is-boxed {
        opacity: 1;
        pointer-events: auto;
        -webkit-transform: translateY(0);
                transform: translateY(0);
}
.navbar-menu {
    flex-grow: 1;
    flex-shrink: 0;
}
.navbar-start {
    justify-content: flex-start;
    margin-right: auto;
}
.navbar-end {
    justify-content: flex-end;
    margin-left: auto;
}
.navbar-dropdown {
    background-color: white;
    border-bottom-left-radius: 6px;
    border-bottom-right-radius: 6px;
    border-top: 2px solid #dbdbdb;
    box-shadow: 0 8px 8px rgba(10, 10, 10, 0.1);
    display: none;
    font-size: 0.875rem;
    left: 0;
    min-width: 100%;
    position: absolute;
    top: 100%;
    z-index: 20;
}
.navbar-dropdown .navbar-item {
      padding: 0.375rem 1rem;
      white-space: nowrap;
}
.navbar-dropdown a.navbar-item {
      padding-right: 3rem;
}
.navbar-dropdown a.navbar-item:hover {
        background-color: whitesmoke;
        color: #0a0a0a;
}
.navbar-dropdown a.navbar-item.is-active {
        background-color: whitesmoke;
        color: #3273dc;
}
.navbar.is-spaced .navbar-dropdown, .navbar-dropdown.is-boxed {
      border-radius: 6px;
      border-top: none;
      box-shadow: 0 8px 8px rgba(10, 10, 10, 0.1), 0 0 0 1px rgba(10, 10, 10, 0.1);
      display: block;
      opacity: 0;
      pointer-events: none;
      top: calc(100% + (-4px));
      -webkit-transform: translateY(-5px);
              transform: translateY(-5px);
      transition-duration: 86ms;
      transition-property: opacity, -webkit-transform;
      transition-property: opacity, transform;
      transition-property: opacity, transform, -webkit-transform;
}
.navbar-dropdown.is-right {
      left: auto;
      right: 0;
}
.navbar-divider {
    display: block;
}
.navbar > .container .navbar-brand,
  .container > .navbar .navbar-brand {
    margin-left: -.75rem;
}
.navbar > .container .navbar-menu,
  .container > .navbar .navbar-menu {
    margin-right: -.75rem;
}
.navbar.is-fixed-bottom-desktop, .navbar.is-fixed-top-desktop {
    left: 0;
    position: fixed;
    right: 0;
    z-index: 30;
}
.navbar.is-fixed-bottom-desktop {
    bottom: 0;
}
.navbar.is-fixed-bottom-desktop.has-shadow {
      box-shadow: 0 -2px 3px rgba(10, 10, 10, 0.1);
}
.navbar.is-fixed-top-desktop {
    top: 0;
}
html.has-navbar-fixed-top-desktop,
  body.has-navbar-fixed-top-desktop {
    padding-top: 3.25rem;
}
html.has-navbar-fixed-bottom-desktop,
  body.has-navbar-fixed-bottom-desktop {
    padding-bottom: 3.25rem;
}
html.has-spaced-navbar-fixed-top,
  body.has-spaced-navbar-fixed-top {
    padding-top: 5.25rem;
}
html.has-spaced-navbar-fixed-bottom,
  body.has-spaced-navbar-fixed-bottom {
    padding-bottom: 5.25rem;
}
a.navbar-item.is-active,
  .navbar-link.is-active {
    color: #0a0a0a;
}
a.navbar-item.is-active:not(:hover),
  .navbar-link.is-active:not(:hover) {
    background-color: transparent;
}
.navbar-item.has-dropdown:hover .navbar-link, .navbar-item.has-dropdown.is-active .navbar-link {
    background-color: #fafafa;
}
}
.hero.is-fullheight-with-navbar {
  min-height: calc(100vh - 3.25rem);
}
nav {
  display: none;
}
@media all and (max-width: 800px) {
nav {
    display: block;
}
}

nav {
  display: none;
}

@media all and (max-width: 800px) {
  nav {
    display: block;
  }
}
</style>
