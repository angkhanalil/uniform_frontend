<template>
  <div
    class="tab-pane fade"
    id="ref_project"
    role="tabpanel"
    aria-labelledby="v_ref_project"
  >
    <h5 class="font-18">project tab!</h5>
    <div class="row" v-for="(proj, idx) in projects" :key="idx">
      <!---->
      <div class="col-sm-6 mb-2 mb-sm-0">
        <div class="form-check">
          <input type="checkbox" class="form-check-input" id="task1" />
          <label class="form-check-label" for="task1">
             {{ proj.proj_name }} 
          </label>
        </div>
        <!-- end checkbox -->
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      projects: [],
    }
  },
  async fetch() {
    this.projects = await fetch(
      'http://localhost:8080/project/getprojectcompany?id=' +
        this.$route.query.id
    ).then((res) => res.json())
  },
}
</script>
