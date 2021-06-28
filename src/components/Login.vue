<template>
  <div class="md:h-screen p-20 bg-body">
    <Card class="md:h-full bg-card">
      <div
        class="
          flex flex-col
          md:flex-row
          items-center
          justify-center
          w-full
          md:h-full
        "
      >
        <div class="md:w-1/2 w-full p-16">
          <img
            src="../assets/img-login-2.png"
            alt="img-login"
            class="md:h-auto z-10 relative"
          />
        </div>
        <div class="md:w-1/2 w-full">
          <div>
            <div
              class="
                flex
                items-center
                justify-center
                py-12
                px-4
                sm:px-6
                lg:px-8
              "
            >
              <div class="max-w-md w-full space-y-8 z-10">
                <div class="flex flex-col items-center justify-center">
                  <img
                    src="../assets/usuario2.png"
                    alt="usuario"
                    class="w-1/6"
                  />
                  <h2
                    class="
                      my-2
                      text-center text-3xl
                      font-extrabold
                      text-gray-900
                      m-0
                    "
                  >
                    LOGIN
                  </h2>
                </div>
                <div class="mt-8 space-y-6" action="#" method="POST">
                  <input type="hidden" name="remember" value="true" />
                  <div class="rounded-md shadow-sm -space-y-px">
                    <div class="mb-2">
                      <label for="email-address" class="sr-only"
                        >Username</label
                      >
                      <div class="flex">
                        <span
                          class="
                            color-box-icon
                            inline-flex
                            items-center
                            px-3
                            border border-r-0 border-gray-300
                            text-gray-500 text-sm
                          "
                        >
                          <span class="material-icons text-white">
                            person
                          </span>
                        </span>
                        <input
                          id="email-address"
                          name="email"
                          type="email"
                          autocomplete="email"
                          class="
                            padding-input
                            appearance-none
                            rounded-none
                            relative
                            block
                            w-full
                            px-3
                            py-2
                            border border-gray-300
                            placeholder-gray-500
                            text-gray-900
                            focus:outline-none
                            focus:ring-indigo-500
                            focus:border-indigo-500
                            focus:z-10
                            sm:text-sm
                          "
                          placeholder="Username"
                        />
                      </div>
                    </div>
                    <div>
                      <label for="password" class="sr-only">Password</label>
                      <div class="flex">
                        <span
                          class="
                            color-box-icon
                            inline-flex
                            items-center
                            px-3
                            border border-r-0 border-gray-300
                            text-gray-500 text-sm
                          "
                        >
                          <span class="material-icons text-white"> lock </span>
                        </span>
                        <input
                          id="password"
                          name="password"
                          type="password"
                          autocomplete="current-password"
                          class="
                            padding-input
                            appearance-none
                            rounded-none
                            relative
                            block
                            w-full
                            px-3
                            py-2
                            border border-gray-300
                            placeholder-gray-500
                            text-gray-900
                            focus:outline-none
                            focus:ring-indigo-500
                            focus:border-indigo-500
                            focus:z-10
                            sm:text-sm
                          "
                          placeholder="Password"
                        />
                      </div>
                    </div>
                  </div>

                  <div class="flex items-center justify-between">
                    <div class="flex items-center">
                      <input
                        id="remember_me"
                        name="remember_me"
                        type="checkbox"
                        class="
                          h-4
                          w-4
                          text-indigo-600
                          focus:ring-indigo-500
                          border-gray-300
                          rounded
                        "
                      />
                      <label
                        for="remember_me"
                        class="ml-2 block text-sm text-gray-900"
                      >
                        Remember me
                      </label>
                    </div>

                    <div class="text-sm">
                      <a
                        href="#"
                        class="
                          font-medium
                          text-indigo-600
                          hover:text-indigo-500
                        "
                      >
                        Forgot your password?
                      </a>
                    </div>
                  </div>

                  <div>
                    <router-link to="/store"
                      ><button
                        type="submit"
                        class="
                          style-button
                          hover:opacity-90
                          group
                          relative
                          w-full
                          flex
                          justify-center
                          py-2
                          px-4
                          border border-transparent
                          text-sm
                          font-medium
                          text-white
                          focus:outline-none
                        "
                      >
                        Sign in
                      </button></router-link
                    >
                  </div>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </Card>
  </div>
</template>

<script>
import Card from "../components/ui/Card.vue";
export default {
  data() {
    return {};
  },
  components: {
    Card,
  },
};
</script>

<style>
.padding-input {
  padding: 19px 10px !important;
}
.style-button {
  padding: 19px 10px !important;
  background: #48cdfb;
}
.color-box-icon {
  background: #48cdfb;
}
.bg-card::after {
  content: "";
  position: absolute;
  background-image: url("../assets/bg-part-1.png");
  background-repeat: no-repeat;
  background-size: cover;
  width: 100%;
  height: 275px;
  top: 0px;
  left: 0px;
}

.bg-body::before {
  content: "";
  position: absolute;
  background-image: url("../assets/bg-part-22.png");
  background-repeat: no-repeat;
  background-size: cover;
  width: 500px;
  height: 400px;
  bottom: -197px;
  right: 0;
}
@media (min-width: 768px) {
  .bg-card::after {
    width: 500px;
  }
  .bg-body::before {
    bottom: 0 !important;
  }
}
</style>