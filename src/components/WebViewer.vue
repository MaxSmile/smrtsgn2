<template>
  <input type="file" name="file" id="file" v-on:change="changePDF($event)" accept="application/pdf">
  <div id="webviewer" ref="viewer"></div>
</template>

<script>
import { ref, onMounted } from 'vue';
import WebViewer from '@pdftron/webviewer';

export default {
  name: 'WebViewer',
  methods:{
    changePDF : function(event){
      console.log(event.target.files[0].name)
      console.log(event.target.files[0].type)
      // this.url = window.location.href
      // console.log(this.url)
    }
  },
  props: { initialDoc: { type: String } },
  setup(props) {
    const viewer = ref(null);
    onMounted(() => {
      const path = `${process.env.BASE_URL}webviewer`;
      WebViewer({ path, initialDoc: props.initialDoc }, viewer.value);
    });

    return {
      viewer,

    };
  },
  data(){
    return{
      // url:''
    }
  }
};
</script>

<style>
#webviewer {
  height: 800px;
}
</style>
