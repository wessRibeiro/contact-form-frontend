<template>
  <Header/>
  <router-view/>
  <Footer/>
</template>
<script>

import Header from '@/components/Header.vue'
import Footer from '@/components/Footer.vue'


export default {
  components: {
    Header,
    Footer,
  }
}
</script>

<style type="text/css">
.btn .fas, .btn .fab, .btn .far {
  margin-left: 3px;
}
input::placeholder{
  color: #cccccc !important;
  opacity: 1;
}
textarea::placeholder{
  color: #cccccc !important;
  opacity: 1;
}
input, textarea{
  color: #ffffff !important;
}


h2 {
  color: #1f4280;
}

h6 {
  line-height: 1.7;
}

footer.page-footer {
  margin-top: 0px;
  padding-top: 1em;
}

footer {
  background-color: #EE3965 !important;
}

.pink-text {
  color: #EE3965 !important;
}

body {
  background-color: #eee;
}

.btn.pink-gradient {
  color: #fff !important;
}

.map-container-section {
  overflow: hidden;
  padding-bottom:56.25%;
  position: relative;
  height: 0;
}

.map-container-section iframe {
  left: 0;
  top: 72px;
  height: 100%;
  width: 100%;
  position: absolute;
}
.md-form label{
  color: #ffffff !important;
}
.pink-gradient {
  background: linear-gradient(278deg, #1f4280, #ee3965) !important;
}
.message-form-blue{
  color: #FFFFFF;
  border: 1px solid #1f4280;
  background-color: #1f4280;
  border-radius: 10px;
  padding: 1em;
  margin-bottom: 1em;
}
.message-form-blue::after {
  content: '';
  position: absolute;
  width: 0;
  height: 0;
  border-top: 25px solid #1f4280;
  border-left: 20px solid transparent;
  border-right: 11px solid transparent;
  top: 0px;
  left: -5px;
}
.message-blue {
  position: relative;
  margin-left: 20px;
  margin-bottom: 10px;
  padding: 10px;
  background-color: #A8DDFD;
  width: 200px;
  height: 50px;
  text-align: left;
  font: 400 .9em 'Open Sans', sans-serif;
  border: 1px solid #97C6E3;
  border-radius: 10px;
}

.message-pink {
  color: #FFFFFF;
  position: relative;
  margin-bottom: 1em;
  padding: 10px;
  background-color: #EE3965;
  width: auto;
  height: auto;
  text-align: left;
  font: 500 1rem 'Open Sans', sans-serif;
  border: 1px solid #EE3965;
  border-radius: 10px;
  float: right;
}

.message-content {
  padding: 5px;
  margin: 0;
}

.message-blue:after {
  content: '';
  position: absolute;
  width: 0;
  height: 0;
  border-top: 15px solid #A8DDFD;
  border-left: 15px solid transparent;
  border-right: 15px solid transparent;
  top: 0;
  left: -15px;
}

.message-blue:before {
  content: '';
  position: absolute;
  width: 0;
  height: 0;
  border-top: 17px solid #97C6E3;
  border-left: 16px solid transparent;
  border-right: 16px solid transparent;
  top: -1px;
  left: -17px;
}

.message-pink:after {
  content: '';
  position: absolute;
  width: 0;
  height: 0;
  border-bottom: 15px solid transparent;
  border-left: 15px solid transparent;
  border-right: 15px solid transparent;
  top: 0;
  right: -15px;
}

.message-pink:before {
  content: '';
  position: absolute;
  width: 0;
  height: 0;
  border-top: 20px solid #EE3965;
  border-left: 16px solid transparent;
  border-right: 24px solid transparent;
  top: -1px;
  right: -25px;
}

</style>
