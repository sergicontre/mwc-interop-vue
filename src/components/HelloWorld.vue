<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
     <h2>Seamlessly interoperable</h2>
    <p>Here an example of how Web Component work with Vue:</p>
    <ul>
      <li> Vue can set properties ⬇️ to Web Component from Vue component </li>
      <li> Vue can listen ⬆️ events from Web Component </li>
    </ul>
    <mwc-slider
        step="5"
        pin
        markers
        max="5"
        :value="sliderValue"
        @input="sendInfo">
    </mwc-slider>
    <p> Value from slider: <b>{{ info }}</b> </p>

  </div>
</template>

<script>

import '@material/mwc-slider';

export default {
  name: 'HelloWorld',
  props: {
    msg: String,
    sliderValue: {
      type: Number,
      default: 3
    }
  },
  data: function () {
		return {
			info: 3
    };
	},
  methods: {
		sendInfo: function (event) {
			if (event.detail) {
				this.info = event.detail.value;
			}
		}
	}
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
