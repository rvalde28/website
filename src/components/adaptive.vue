<template>
  <div class="example-modal-content">
    <img :src="photoObj.path">
    <div class="image-text-wrapper">
      <p>South Texas College - Nursing & Allied Health Campus, McAllen, Texas</p>
    </div>

  </div>
</template>

<script>
export default {
  props: ['photoObj']
}
</script>