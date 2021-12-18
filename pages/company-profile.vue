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
              <li class="breadcrumb-item active">Company Infomation</li>
            </ol>
          </div>
          <h4 class="page-title">Company</h4>
        </div>
      </div>
    </div>
    <!-- end page title -->
    <div class="row mt-3">
      <div class="col-12">
        <div class="card bg-primary">
          <div class="card-body profile-user-box">
            <div class="row">
              <div class="col-sm-8">
                <div class="row align-items-center">
                  <div class="col-auto">
                    <div class="avatar-lg">
                      <img
                        src="assets/images/users/avatar-2.jpg"
                        alt=""
                        class="rounded-circle img-thumbnail"
                      />
                    </div>
                  </div>
                  <div class="col">
                    <div>
                      <h4 class="mt-1 mb-1 text-white">
                        {{ company_data.company_name }}
                        {{ this.$route.query.id }}
                      </h4>
                      <p class="font-13 text-white-50">
                        Authorised Brand Seller
                      </p>

                      <ul class="mb-0 list-inline text-light">
                        <li class="list-inline-item me-3">
                          <h5 class="mb-1">$ 25,184</h5>
                          <p class="mb-0 font-13 text-white-50">
                            Total Employee
                          </p>
                        </li>
                        <li class="list-inline-item">
                          <h5 class="mb-1">5482</h5>
                          <p class="mb-0 font-13 text-white-50">
                            Total of Female
                          </p>
                        </li>
                        <li class="list-inline-item">
                          <h5 class="mb-1">5482</h5>
                          <p class="mb-0 font-13 text-white-50">
                            Total of Male
                          </p>
                        </li>
                      </ul>
                    </div>
                  </div>
                </div>
              </div>
              <div class="col-sm-4">
                <div class="text-center mt-sm-0 mt-3 text-sm-end">
                  <button type="button" class="btn btn-light">
                    <i class="mdi mdi-account-edit me-1"></i> Edit Profile
                  </button>
                </div>
              </div>
            </div>
            <!-- end col-->
            <!-- end col-->
          </div>
        </div>
      </div>
    </div>
    <!-- Right Sidebar -->
    <div class="row mt-3">
      <!-- Right Sidebar -->
      <div class="col-12">
        <div class="card">
          <div class="card-body">
            <!-- Left sidebar -->
            <div class="page-aside-left">
              <div class="nav flex-column nav-pills mt-3">
                <a
                  href="#ref_project"
                  aria-selected="true"
                  id="v_ref_project"
                  data-bs-toggle="pill"
                  aria-expanded="false"
                  role="tablist"
                  class="nav-link"
                  aria-controls="ref_project"
                  ><i class="dripicons-star me-2"></i>Projects</a
                >
                <a
                  href="#ref_products"
                  aria-selected="false"
                  id="v_ref_products"
                  data-bs-toggle="pill"
                  aria-expanded="false"
                  role="tablist"
                  class="nav-link"
                  aria-controls="ref_products"
                  ><i class="dripicons-clock me-2"></i>Products</a
                >
                <a
                  href="#ref_products_set"
                  aria-selected="false"
                  id="v_ref_products_set"
                  data-bs-toggle="pill"
                  aria-expanded="false"
                  role="tablist"
                  class="nav-link"
                  aria-controls="ref_products_set"
                  ><i class="dripicons-document me-2"></i>Products Set<span
                    class="badge badge-info-lighten float-end ms-2"
                    >32</span
                  ></a
                >
                <a
                  href="#ref_employee"
                  aria-selected="false"
                  id="v_ref_employee"
                  data-bs-toggle="pill"
                  aria-expanded="false"
                  role="tablist"
                  class="nav-link"
                  aria-controls="ref_employee"
                  ><i class="dripicons-clock me-2"></i>Employee</a
                >
              </div>
            </div>
            <div class="page-aside-right">
              <div class="mt-3">
                <div class="tab-content">
                  <ProjectsComponent />
                  <ProductsComponent />
                  <ProductSetComponent />
                  <EmployeeComponent />
                </div> 
                <hr />
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>
<script>
import ProjectsComponent from '@/components/company/project'
import ProductsComponent from '@/components/company/products'
import ProductSetComponent from '@/components/company/productset'
import EmployeeComponent from '@/components/company/employee'
export default {
  layout: 'landing',
  components: {
    ProjectsComponent,
    ProductsComponent,
    ProductSetComponent,
    EmployeeComponent,
  },
  data() {
    return {
      company_data: '',
    }
  },
  async fetch() {
    this.company_data = await fetch(
      'http://localhost:8080/company/getcompany?id=' + this.$route.query.id
    ).then((res_pd) => res_pd.json())
  },
}
</script>