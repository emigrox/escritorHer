<template>
  <v-app>
    <ejs-pdfviewer
      id="pdfViewer"
      :serviceUrl="serviceUrl"
      :documentPath="docPath"
    >
    </ejs-pdfviewer>
  </v-app>
</template>
<script>
import Vue from "vue";
import {
  PdfViewerPlugin,
  Toolbar,
  Magnification,
  Navigation,
  LinkAnnotation,
  BookmarkView,
  ThumbnailView,
  Print,
  TextSelection,
  TextSearch,
} from "@syncfusion/ej2-vue-pdfviewer";
Vue.use(PdfViewerPlugin);

export default {
  

  data: () => {

    return {
      serviceUrl:
        "https://ej2services.syncfusion.com/production/web-services/api/pdfviewer",
      docPath: "@assets/marta.pdf",
    };
  },
  provide: {
    PdfViewer: [
      Toolbar,
      Magnification,
      Navigation,
      LinkAnnotation,
      BookmarkView,
      ThumbnailView,
      Print,
      TextSelection,
      TextSearch,
    ],
  },
};
</script>

<style>
@import "../../node_modules/@syncfusion/ej2-pdfviewer/styles/material.css";
@import '../../node_modules/@syncfusion/ej2-base/styles/material.css';  
@import '../../node_modules/@syncfusion/ej2-buttons/styles/material.css';
@import '../../node_modules/@syncfusion/ej2-dropdowns/styles/material.css';  
@import '../../node_modules/@syncfusion/ej2-inputs/styles/material.css';  
@import '../../node_modules/@syncfusion/ej2-navigations/styles/material.css';
@import '../../node_modules/@syncfusion/ej2-popups/styles/material.css';
@import '../../node_modules/@syncfusion/ej2-splitbuttons/styles/material.css';
#pdfViewer {
  height: 640px;
}
</style>



