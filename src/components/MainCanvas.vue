<template lang="pug">
div
    .img_list
        img(v-for="(row,index) in images" v-bind:id="'image_'+index" :src='imgPath(row)' @click="addObject(index)")
    canvas#canvas(width=1200 height=960)
</template>
<style scoped>
    .img_list{
        display: inline;
        
    }
    .img_list img {
        max-width: 50px;
    }
</style>

<script>

export default {
  data(){
      return {
          canvas: null,
          images: [
                    '五星旗.png',
                    '伸縮棍.png',
                    '大聲公學生.png',
                    '抗議布條人.png',
                    '旁觀女.png',
                    '旁觀學生A.png',
                    '旁觀學生B.png',
                    '旁觀手機女.png',
                    '旁觀手機女2.png',
                    '旁觀手機女2.png',
                    '旁觀相機男.png',
                    '旁觀相機男2.png',
                    '獨立旗人.png',
                    '白狼軍丙.png',
                    '白狼軍乙.png',
                    '白狼軍甲.png',
                    '被打學生.png',
                    '警察.png',
                    '警察遲鈍.png',
                    '路人1.png',
                    '路人大嬸.png',
                    '路人帽女.png',
                    '路人帽男.png',
                    '路人帽男.png',
                    '黑衣人_攻擊.png',
                    '黑衣人.png',
          ]
      }
  },
  methods: {
      imgPath: (name) =>{
          return `static/images/${name}`
      },
      addObject : (id) =>{
          let image_id = `image_${id}`
          var imgElement = document.getElementById(image_id);
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
