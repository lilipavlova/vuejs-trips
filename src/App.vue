<template>
  <div id="app">

    <div class="main">
     <app-navigation  @onAuth="isAuth = $event" :isAuth="isAuth"></app-navigation>
     <router-view @onAuth="isAuth = $event" :isAuth="isAuth"></router-view>

    </div>

    <app-footer></app-footer>
  </div>
</template>

<script>
import AppFooter from './components/core/Footer'
import AppNavigation from "./components/core/Navigation"
import { appKey } from './storage';

export default {
  name: 'App',
  data: function(){
    return {
       isAuth: localStorage.getItem('authToken' + appKey) !== null
    };
  },
  components: {
    AppNavigation,
    AppFooter
  }

}
</script>


<style>
@import url("https://fonts.googleapis.com/css?family=Lato&display=swap");
body {
    font-family: "Lato", sans-serif;
}

#app {
    font-family: 'Lato', Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    text-align: center;
    color: #2c3e50;
}


/** ************************************** **/

footer {
    background-color: #303440;
    color: white;
    bottom: 0;
    display: flex;
    position:fixed;
    left:0;
     width:100%;
     
}

footer div {
  display: contents;
}

footer .section-header {
    border-bottom: 3px solid #303440;
    margin: 1rem;
    color: white;
}

footer span {
    background: #303440;
    color: white;
    font-size: 26px;
    border-radius: 6px 6px 0 0;
    padding: 3px 17px;
}

footer section {
    width: 20%;
    display: inline-block;
    margin: 0.5em auto;
    vertical-align: top;
}

footer a {
    text-decoration: none;
    color: white;
}

footer div section {
    display: inline-block;
    vertical-align: top;
}

footer div section {
    width: 20%;
    text-align: right;
}

footer div .social-icons a {
    font-size: 26px;
    margin: 0.3em;
    padding: 10px;
}

footer .svg-inline--fa {
    overflow: visible;
    width: 1em;
    display: inline-block;
    font-size: inherit;
    height: 1em;
    vertical-align: -0.125em;
}

/** ************************************** **/

.main div.navigation {
    background: #303440;
    font-size: 20px;
    text-align: left;
    display: flex;
}

.main div.navigation ul {
    display: inline-block;
    text-align: left;
}

.main div.navigation ul:nth-child(1) {
    width: 75%;
}

.main div.navigation ul:nth-child(2) {
    width: 20%;
    text-align: right;
}

.main div.navigation li {
    list-style: none;
    display: inline-block;
    margin-right: 6%;
}



.main div.navigation li a {
    padding: 1%;
    color: white;
    text-decoration: none;
    font-weight: bold;
    display: inline-table;
}

.main div.navigation li a:hover {
    text-decoration: underline;
}

.main div.main-content {
    display: flex;
}

.main div.main-content .content-navigation {
    width: 20%;
    border-right: 3px solid whitesmoke;
    border-left: 3px solid whitesmoke;
}

.main div.main-content .subject-info {
    padding: 1%;
}

.main div.main-content .subject-info p {
    font-size: 18px;
}

.main .main-content .content-navigation ul {
    margin: 0;
    padding: 0;
}

.main div.main-content .content-navigation ul li {
    list-style-type: none;
    padding: 10%;
    font-size: 23px;
    cursor: pointer;
    text-align: left;
}

.main div.main-content .content-navigation ul li:hover {
    background: whitesmoke;
}

.main div.main-content .content-navigation ul li:active {
    border-right: 5px solid #303440;
}

.main div.main-content .content-navigation ul li:nth-child(3) {
    border-right: 5px solid #303440;
}

.main div.main-content .content-navigation ul li a {
    color: black;
    text-decoration: none;
}

.main .content-info {
    width: 80%;
    padding: 1%;
    font-size: 18px;
    display: block;
}

.main .content-info .user-form input {
    padding: 1%;
    width: 25%;
    border: none;
    border-bottom: 1px solid black;
    font-size: 16px;
    font-family: inherit;
}

.main .content-info .user-form input:focus {
    background: rgb(255, 248, 198);
}

.main .content-info .user-form .form-group {
    margin-bottom: 1%;
}

.main .content-info .user-form .form-group img {
    vertical-align: bottom;
}

.main .content-info .user-form button {
    padding: 1%;
    background: #303440;
    color: white;
    border: none;
    width: 10%;
    font-size: 16px;
    cursor: pointer;
}

.main .content-info .user-links a {
    color: black;
    text-decoration: none;
    font-weight: normal;
    margin: 2%;
}

.main .content-info .user-links a:hover {
    color: #303440;
    text-decoration: underline;
}

.main .content-info .user-links .active-route {
    color: #303440;
    text-decoration: underline;
}

/** ************************************** **/

.btn {
    padding: 1%;
    background: #303440;
    color: white;
    border: none;
    width: 10%;
    font-size: 16px;
    cursor: pointer;
    border: 1px solid white;
    display: block;
    margin: 0 auto;
    margin-top: 1%;
    margin-bottom: 1%;
}

.btn:hover {
    color: #303440;
    background: white;
    border: 1px solid #303440;
    text-decoration: underline;
}

div.form-group {
    margin-top: 1%;
    margin-bottom: 1%;
}

div.form-group input, option, select {
    font-size: 18px;
    padding: 1%;
    width: 25%;
    border: none;
    border-bottom: 1px solid black;
    font-size: 16px;
    font-family: inherit;
    text-align: center;
	text-align-last: center;
}

select {
    -webkit-appearance: none;
    -moz-appearance: none;
    text-indent: 1px;
    text-overflow: '';
}

.content-preview {
    text-align: left;
    word-wrap: break-word;
    display: block;
    width: 100%;
}

/** ************************************** **/

/** ************************************** **/
</style>
