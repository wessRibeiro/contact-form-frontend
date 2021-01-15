<template>
  <footer class="page-footer lighten-3 text-center text-md-left">
    <div class="text-center py-3 wow fadeIn" data-wow-delay="0.3s">
      <div class="container-fluid">
                    <span>
                        Rua Capitão Antônio Rosa, 376 —  {{ date }}
                    </span>
        <a href="https://netshow.me">&nbsp; Copyright © Netshow.me</a>
      </div>
    </div>
  </footer>
</template>

<script>
import moment from "moment";

export default {
  name: "Footer",
  data() {
    return {
      date: moment(new Date()).format("DD/MM/YYYY"),
    }
  }
}

</script>

<style scoped>

</style>