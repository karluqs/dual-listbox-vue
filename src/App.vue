<template>
  <div id="app">
    <div class="container mt-3">
      <DualListBox
        :source="source"
        :destination="destination"
        label="label"
        @onChangeList="onChangeList"
      />
      <div class="row">
        <div class="col-sm-6">
          <pre>{{source}}</pre>
        </div>
        <div class="col-sm-6">
          <pre>{{destination}}</pre>
        </div>
      </div>
      <div class="btn btn-primary" @click="display">Display</div>
    </div>
  </div>
</template>

<script>
import DualListBox from "./components/DualListBox.vue";
import { source, destination } from "./data";
export default {
  name: "App",
  components: {
    DualListBox
  },
  data: function() {
    return {
      source,
      destination
    };
  },
  methods: {
    display: function() {
      console.log("source", this.source);
      console.log("destination", this.destination);
    },
    onChangeList: function({ source, destination }) {
      this.source = source;
      this.destination = destination;
    }
  }
};
</script>

<style>
.container {
  max-width: 1170px;
  margin: 0 auto;
}

.row {
  display: flex;
}
.col-sm-6 {
  padding: 0 1rem;
  width: 100%;
}
</style>

