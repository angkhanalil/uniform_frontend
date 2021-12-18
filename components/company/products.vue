<template>
  <div
    class="tab-pane fade"
    id="ref_products"
    role="tabpanel"
    aria-labelledby="v_ref_products"
  >
    <h5 class="font-18">products tab!</h5>
    <div class="row">
      <div class="col-12">
        <div class="row row-cols-1 row-cols-md-4 g-3">
          <div class="col" v-for="(prod, idx) in products" :key="idx">
            <div class="card">
              <img
                src="assets/images/small/small-4.jpg"
                class="card-img-top"
                alt="Card image cap"
              />
              <div class="card-body">
                <h5 class="card-title">
                  <nuxt-link  :to="{ path: '/productdetail', query: { id: prod.company_id , pdid : prod.clothing_cat_id } }" >
                    {{ prod.clothing_cat_name }}
                  </nuxt-link>
                </h5>
                <p class="card-text"></p>
                <!--  <p class="card-text">
                  <small class="text-muted">Last updated 3 mins ago</small>
                </p>-->
              </div>
            </div>
          </div>
        </div>
      </div>
      <!-- end col-->
    </div>
    <!-- end row -->
  </div>
</template>
<script>
export default {
  data() {
    return {
      products: [],
    }
  },
  async fetch() {
    this.products = await fetch(
      'http://localhost:8080/clothingcat/getclothingcat_company?id=' +
        this.$route.query.id
    ).then((res) => res.json())
  },
}
//
</script>