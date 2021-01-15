<template>
  <div :class="'container message-'+color">
    <div class="message-content">
      <slot/>
    </div>
  </div>
</template>

<script>
export default {
  name: "MessageBox",
  props: {
    color: String,
  }
}
</script>
