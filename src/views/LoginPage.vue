<template>
  <div class="container-fluid">
    <div class="row no-gutter">
      <!-- The image half -->
      <div class="col-md-6 d-none d-md-flex bg-image"></div>

      <!-- The content half -->
      <div class="col-md-6 bg-light">
        <div class="login d-flex align-items-center py-5">
          <!-- Demo content-->
          <div class="container">
            <div class="row">
              <div class="col-lg-10 col-xl-7 mx-auto">
                <h3 class="display-4">Google Sign In</h3>
                <p class="text-muted mb-4">
                  Enjoy shopping every single day with us!
                </p>
                <form @submit="onSubmit">
                  <div class="form-group mb-3"></div>
                  <div class="form-group mb-3"></div>
                  <div class="custom-control custom-checkbox mb-3">
                    <input
                      id="customCheck1"
                      type="checkbox"
                      checked
                      class="custom-control-input"
                    />
                    <label
                      for="customCheck1"
                      class="custom-control-label"
                    ></label>
                  </div>
                  <button
                    type="submit"
                    class="btn btn-primary btn-block text-uppercase mb-2 rounded-pill shadow-sm"
                  >
                    Sign in
                  </button>
                </form>
              </div>
            </div>
          </div>
          <!-- End -->
        </div>
      </div>
      <!-- End -->
    </div>
  </div>
</template>
<script>
import { mapActions } from "vuex";
export default {
  name: "Login",
  components: {},
  mounted() {
    if (localStorage.USER) this.$router.push("/")
  },
  methods: {
    ...mapActions("user", ["login"]),
    onSubmit(e) {
      e.preventDefault();
      this.login().then(() => {
        this.$router.go();
      })
    },
  },
};
</script>
<style scoped>
.login,
.image {
  min-height: 100vh;
}

.bg-image {
  background-image: url("https://res.cloudinary.com/mhmd/image/upload/v1555917661/art-colorful-contemporary-2047905_dxtao7.jpg");
  background-size: cover;
  background-position: center center;
}
</style>