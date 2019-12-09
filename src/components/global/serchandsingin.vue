<template>
  <div class="container">
    <div class="row">
      <div class="col-12 text-center">
        <div>
          <b-navbar toggleable="lg" type="dark" variant="info">
            <i class="fas fa-space-shuttle" fa-xs style="color:#dd63f3;"></i>

            <b-navbar-brand href="#">spatium</b-navbar-brand>

            <b-navbar-toggle target="nav-collapse"></b-navbar-toggle>

            <b-collapse id="nav-collapse" is-nav>
              <!-- Right aligned nav items -->
              <b-navbar-nav class="ml-auto">
                <b-nav-form>
                  <b-form-input size="sm" class="mr-sm-2" placeholder="Search"></b-form-input>
                  <i class="fas fa-search"></i> 
                </b-nav-form>

                <b-nav-item-dropdown left>
                  <!-- Using 'button-content' slot -->
                  <template v-slot:button-content>
                    <em>SignIn & or SignUp</em>
                  </template>
                  <b-dropdown-item href="#">Profile</b-dropdown-item>
                  <b-dropdown-item href="#">Sign Out</b-dropdown-item>
                </b-nav-item-dropdown>
              </b-navbar-nav>
            </b-collapse>
          </b-navbar>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "serchandsingin"
};
</script>

<style lang="scss" scoped>
.container {
  .row {
    .ml-auto,
    .mx-auto {
      margin-left: 6% !important;
    }
    @media (min-width: 576px) {
      .form-inline .form-control {
        display: inline-block;
        width: 692px;
        vertical-align: middle;
      }
    }
    .fa-search:before {
    left: 53rem;
    position: absolute;
    content: "\f002";
    top: 1.10rem;
}
  }
}
</style>
