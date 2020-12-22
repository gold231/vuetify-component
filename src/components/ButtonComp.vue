<template>
  <div class="comp" :style="div_style">
    <p :style="text_style">${{ styles.text }}</p>
    <p :style="select_style">{{ styles.select }}</p>
  </div>
</template>

<script>
export default {
  name: 'ButtonComp',
  props: {
      styles: Object
  },
  computed: {
    // button field's styles
    div_style () {
      var divStr = ''; // button field's styles variable
      
      divStr += 'width:' + this.styles.oval + 'px;'; // oval size style

      // discriminate that state is "view" or "edit"
      if (this.styles.state == "view") {
        divStr += 'border: 2px solid blue;'
      } else {
        //outline color style
        if (this.styles.outline == "aligned") {
          divStr += 'border: 2px solid blue;'
        } else if (this.styles.outline == "misaligned") {
          divStr += 'border: 2px solid red;'
        } else {
          divStr += 'border: 2px solid black;';
        }
      }

      // if fill color is white, text color is black or text color is white  
      if (this.styles.fill == "white") {
        divStr += 'color: black;'
      } else {
        divStr += 'color: white;'
      }

      divStr += 'background-color:' + this.styles.fill;

      return divStr;
    },


    // text field's font size style
    text_style() {
      return 'font-size:' + this.styles.text_size + 'px;'
    },

    //select field's font size style
    select_style() {
      return 'font-size:' + this.styles.select_style + 'px;'
    }    
  }
}
</script>

<style scoped lang="scss">
//component's general styles
.comp {   
  text-align: center;
  border-radius: 35px;
  padding: 5px;
  margin: 5px;
  p {
    margin-bottom: 0;
    margin-top: 0;
  }
}
</style>
