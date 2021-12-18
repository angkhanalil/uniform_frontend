<template>
  <div>
    <!-- start page title -->
    <div class="row">
      <div class="col-12">
        <div class="page-title-box">
          <div class="page-title-right">
            <ol class="breadcrumb m-0">
              <li class="breadcrumb-item">
                <a href="javascript: void(0);">Uniforms</a>
              </li>
              <li class="breadcrumb-item">
                <a href="/company">Company</a>
              </li>
              <li class="breadcrumb-item active">Projects List</li>
            </ol>
          </div>
          <h4 class="page-title">Projects</h4>
        </div>
      </div>
    </div>
    <!-- end page title -->

    <div class="row mt-3">
      <div
        class="col-md-6 col-xxl-4"
        v-for="(proj, idx) in projects"
        :key="idx"
      >
        <!-- project card -->
        <div class="card d-block">
          <!-- project-thumbnail -->
          <img
            class="card-img-top"
            style="width: 50%"
            src="assets/images/projects/project-1.jpg"
            alt="project image cap"
          />
          <div class="card-img-overlay">
            <div class="badge bg-secondary text-light p-1">Ongoing</div>
          </div>

          <div class="card-body position-relative">
            <!-- project title-->
            <h4 class="mt-0">
              <a href="#" class="text-title">
                {{ proj.proj_name }}</a
              >
            </h4>
          </div>
          <!-- end card-body-->
        </div>
      </div>
    </div>
  </div>
</template>

<script> 
export default {
  layout: 'landing',
  data() {
    return {
      projects: [],
    }
  },
  created() {
    console.log(this.$route.query.id) // john 
    
  },
  async fetch() {
    this.projects = await fetch(
      'http://localhost:8080/project/getprojectcompany?id=' +
        this.$route.query.id
    ).then((res) => res.json())
  },
}
</script>
