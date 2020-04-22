<template>
  <div class="container" style="width: 80%; padding: 40px; margin: 50px;">
    <div class="card">
      <div class="card-header">Claudinary Integration</div>
      <div class="card-body">
        <div class="col-sm-6" style="float: left;">
          <form>
            <div class="form-group">
              <label for="Font">Font</label>
              <select class="form-control" id="font" v-model="font">
                <option v-for="i in fontArray" :key="i">
                  {{ i }}
                </option>
              </select>
            </div>
            <div class="form-group">
              <label for="Font-size">Font size</label>
              <select class="form-control" id="fontSize" v-model="fontSize">
                <option v-for="i in fontSizeArray" :key="i">
                  {{ i }}
                </option>
              </select>
            </div>
            <div class="form-group">
              <label for="Font-weight">Font weight</label>
              <select class="form-control" id="fontWeight" v-model="fontWeight">
                <option v-for="i in fontWeightArray" :key="i">
                  {{ i }}
                </option>
              </select>
            </div>
            <div class="form-group">
              <label for="Text">Text</label>
              <textarea
                class="form-control"
                id="Text"
                rows="3"
                v-model="text"
              ></textarea>
            </div>
          </form>
        </div>
        <div class="col-sm-6" style="float: right;">
          <img width="100%" height="350px" :src="imgen" />
          <div style="margin-top:25px">URL : {{ imgen }} </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "cloudinar",
  data: () => {
    return {
      font: "Arial",
      fontSize: "100",
      fontWeight: "100",
      text: "OTD&Cloudinary integration",
      cloudynaryIMGURL: "https://res.cloudinary.com/demo/image/upload/l_text:",
      fontWeightArray: [
        "100",
        "200",
        "300",
        "400",
        "500",
        "600",
        "700",
        "800",
        "900",
        "bold",
        "bolder",
      ],
      fontSizeArray: [
        "100",
        "200",
        "300",
        "400",
        "500",
        "600",
        "700",
        "800",
        "900",
      ],
      fontArray: [
        "Arial",
        "Segoe UI",
        "Roboto",
        "Helvetica Neue",
        "Noto Sans",
        "sans - serif",
        "Apple Color Emoji",
        "Segoe UI Emoji",
        "Segoe UI Symbol",
        "Noto Color Emoji",
      ],
    };
  },
  computed: {
    imgen: function() {
      var img =
        this.cloudynaryIMGURL +
        this.font +
        "_" +
        this.fontSize +
        "_" +
        this.fontWeight +
        ":" +
        this.text +
        "/photo-1430609098125-581618d0482f_xvayby";
      return img;
    },
  },
};
</script>
