<template>
  <div class="container">
    <div class="row">
      <div class="col-12 text-center">
        <div>
          <b-navbar toggleable="lg" type="dark" variant="info">
            <i class="fas fa-space-shuttle" fa-lg style="color:#FFC107;"></i>

            <b-navbar-brand href="#">Spatium</b-navbar-brand>

            <b-navbar-toggle target="nav-collapse"></b-navbar-toggle>

            <b-collapse id="nav-collapse" is-nav>
              <!-- Right aligned nav items -->
              <b-navbar-nav class="ml-auto">
                <b-nav-form>
                  <b-form-input
                    size="sm"
                    class="mr-sm-2"
                    placeholder="Search"
                  ></b-form-input>
                  <i class="fas fa-search"></i>
                </b-nav-form>

                <b-nav-item-dropdown left>
                  <!-- Using 'button-content' slot -->
                  <template v-slot:button-content>
                    <em>SignIn & or SignUp</em>
                  </template>
                  <b-dropdown-item class="ret"
                    >Returning Customer</b-dropdown-item
                  >
                  <button class="btn btn-danger Sign">SignIn</button>
                  <h6 class="infor">Don't have an account?</h6>
                  <p class="line"></p>
                  <b-dropdown-item href="https://www.google.com" class="signup"
                    >SignUp</b-dropdown-item
                  >
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
  background-color: #e26df6 !important;
  .bg-info {
    background-color: #e26df6 !important;
  }
  .row {
    .ml-auto,
    .mx-auto {
      margin-left: 6% !important;
    }
    .fa-space-shuttle {
      position: absolute;
      left: -0.7%;
      top: 40%;
    }
    @media (min-width: 576px) {
      .form-inline .form-control {
        display: inline-block;
        width: 692px;
        vertical-align: middle;
      }
    }
    .fa-search:before {
      left: 52rem;
      position: absolute;
      content: "\f002";
      top: 1.1rem;
    }
    .ret {
      text-align: center;
      font-size: 11px;
    }
    .Sign {
      text-align: center;
      margin: 10px;
      margin-left: 29%;
    }
    .infor {
      text-align: center;
      font-size: 12px;
      border: 2px solid rgba(0, 0, 0, 0.2);
    }
    .line {
      border-bottom: 1px solid rgb(226, 229, 241);
    }
    .signup {
      text-align: center;
      font-size: 13px;
      color: red;
    }
  }
}
</style>
