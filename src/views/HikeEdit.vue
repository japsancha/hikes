/* eslint-disable */
<template>
  <div class="hike-edit container">
      <h2>Edit hike</h2>
    <form v-on:submit="updateHike">
      <div class="form-group">
        <label for="edit-name">Name</label>
        <input class="form-control" id="edit-name" v-model="hike.name" required/>
      </div>
      <div class="form-group">
        <label for="edit-link">Link</label>
        <input class="form-control" id="edit-link" v-model="hike.link" required/>
      </div>
      <div class="form-group">
        <label for="edit-elevation">Elevation</label>
        <input class="form-control" id="edit-elevation" v-model="hike.elevation" required/>
      </div>

      <div class="form-group">
        <label for="edit-latitude">Latitude</label>
        <input class="form-control" id="edit-latitude" v-model="hike.latitude" required/>
      </div>
      <div class="form-group">
        <label for="edit-name">Longitude</label>
        <input class="form-control" id="edit-longitude" v-model="hike.longitude" required/>
      </div>
      
      <div class="form-group">
        <label for="edit-length">Length</label>
         <input class="form-control" id="edit-length" v-model="hike.length"/>       
      </div>
      <button type="submit" class="btn btn-primary act">Save</button>
      <router-link class="btn btn-default act" v-bind:to="'/'">Cancel</router-link>
    </form>
  </div>
</template>

<script>
import { mapList } from "../data";
export default {
  name: "hikeEdit",
  data() {
    return { hike: mapList.getItemByKey(this.$route.params.hike_id), hikes: mapList };
  },
  methods: {
    updateHike: function() {
      this.hikes.update(this.hike);
      this.$router.push("/");
    }
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.form-group {
  max-width: 500px;
}
.act  {
  margin-top: 20px;
}
.actions {
  padding: 10px 0;
}
form div {
  margin:auto;
}

</style>
