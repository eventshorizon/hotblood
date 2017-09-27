<template lang="pug">
div
    canvas#canvas(width=1200 height=960)
    img#img1(src='static/images/路人1.png' @click="addObject('img1')")
    img#img2(src='static/images/路人大嬸.png' @click="addObject('img2')")
</template>
<script>

export default {
  data(){
      return {
          canvas: null,
          images: [
                
          ]
      }
  },
  methods: {
      addObject : (id) =>{
          var imgElement = document.getElementById(id);
        var imgInstance = new fabric.Image(imgElement, {
        left: 100,
        top: 100,
        angle: 0,
        opacity: 1
        });
        this.canvas.add(imgInstance);
      },
  },
  mounted: () => {
      this.canvas = new fabric.Canvas('canvas');
        
  }
}
</script>
