<script setup>
import { ref } from "vue";

const { login } = useSanctumAuth()

const credentials = ref({
    email: "",
    password: "",
    remember: true,
});

const errors = ref([]);

const doLogin = async () =>  {
    try {
        await login(credentials.value);
        router.push("/");
    } catch (error) {
        errors.value = error.data.errors;
        console.error('catch',error.response);
    }
}
const clearErrors = () => {
    errors.value = [];
}

</script>

<template>
  <!-- Pages: Sign In: Boxed -->
  <!-- Page Container -->
  <div
    id="page-container"
    class="mx-auto flex min-h-dvh w-full min-w-[320px] flex-col bg-gray-100 dark:bg-gray-900 dark:text-gray-100"
  >
    <!-- Page Content -->
    <main id="page-content" class="flex max-w-full flex-auto flex-col">
      <div
        class="relative mx-auto flex min-h-dvh w-full max-w-10xl items-center justify-center overflow-hidden p-4 lg:p-8"
      >
        <!-- Sign In Section -->
        <section class="w-full max-w-xl py-6">
          <!-- Header -->
          <header class="mb-10 text-center">
            <img
              src="/images/logo.png"
              alt="Logo"
              class="w-28 mx-auto mb-4" />
          </header>
          <!-- END Header -->

          <!-- Sign In Form -->
          <div
            class="flex flex-col overflow-hidden rounded-lg bg-white shadow-sm dark:bg-gray-800 dark:text-gray-100"
          >
            <div class="grow p-5 md:px-16 md:py-12">
              <form class="space-y-6">
                <div class="space-y-1">
                  <label for="email" class="text-sm font-medium">Correo electrónico</label>
                  <input
                    type="email"
                    v-model="credentials.email"
                    @input="clearErrors"
                    id="email"
                    name="email"
                    class="block w-full rounded-lg border border-gray-200 px-5 py-3 leading-6 placeholder-gray-500 focus:border-blue-500 focus:ring focus:ring-blue-500/50 dark:border-gray-600 dark:bg-gray-800 dark:placeholder-gray-400 dark:focus:border-blue-500"
                  />
                  <p class="text-sm text-red-500">{{ errors.email?.toString() }}</p>
                </div>
                <div class="space-y-1">
                  <label for="password" class="text-sm font-medium"
                    >Contraseña</label
                  >
                  <input
                    v-model="credentials.password"
                    @input="clearErrors"
                    type="password"
                    id="password"
                    name="password"
                    class="block w-full rounded-lg border border-gray-200 px-5 py-3 leading-6 placeholder-gray-500 focus:border-blue-500 focus:ring focus:ring-blue-500/50 dark:border-gray-600 dark:bg-gray-800 dark:placeholder-gray-400 dark:focus:border-blue-500"
                  />
                  <p class="text-sm text-red-500">{{ errors?.password?.toString() }}</p>
                </div>
                <div>
                  <div class="mb-5 flex items-center justify-between gap-2">
                    <label class="flex items-center">
                      <input
                        v-model="credentials.remember"
                        type="checkbox"
                        id="remember_me"
                        name="remember_me"
                        class="size-4 rounded border border-gray-200 text-blue-500 focus:border-blue-500 focus:ring focus:ring-blue-500/50 dark:border-gray-600 dark:bg-gray-800 dark:ring-offset-gray-900 dark:checked:border-transparent dark:checked:bg-blue-500 dark:focus:border-blue-500"
                      />
                      <span class="ml-2 text-sm">Recordarme</span>
                    </label>
                    <NuxtLink
                      to="/auth/PasswordReset"
                      class="inline-block text-sm font-medium text-blue-600 hover:text-blue-400 dark:text-blue-400 dark:hover:text-blue-300"
                    >¿Olvidé mi Contraseña?
                    </NuxtLink>
                  </div>
                  <button
                    @click.prevent="doLogin"
                    class="inline-flex w-full items-center justify-center gap-2 rounded-lg border border-blue-700 bg-blue-700 px-6 py-3 font-semibold leading-6 text-white hover:border-blue-600 hover:bg-blue-600 hover:text-white focus:ring focus:ring-blue-400/50 active:border-blue-700 active:bg-blue-700 dark:focus:ring-blue-400/90"
                  >
                    <svg
                      class="hi-mini hi-arrow-uturn-right inline-block size-5 opacity-50"
                      xmlns="http://www.w3.org/2000/svg"
                      viewBox="0 0 20 20"
                      fill="currentColor"
                      aria-hidden="true"
                    >
                      <path
                        fill-rule="evenodd"
                        d="M12.207 2.232a.75.75 0 00.025 1.06l4.146 3.958H6.375a5.375 5.375 0 000 10.75H9.25a.75.75 0 000-1.5H6.375a3.875 3.875 0 010-7.75h10.003l-4.146 3.957a.75.75 0 001.036 1.085l5.5-5.25a.75.75 0 000-1.085l-5.5-5.25a.75.75 0 00-1.06.025z"
                        clip-rule="evenodd"
                      />
                    </svg>
                    <span>Iniciar sesión</span>
                  </button>
                </div>
              </form>
            </div>
          </div>
          <!-- END Sign In Form -->

          <!-- Footer -->
          <div
            class="mt-6 text-center text-sm text-gray-500 dark:text-gray-400"
          >
            Desarrollado por
            <a
              href="#"
              class="font-medium text-blue-600 hover:text-blue-400 dark:text-blue-400 dark:hover:text-blue-300"
              >devConsulting</a
            >
          </div>
          <!-- END Footer -->
        </section>
        <!-- END Sign In Section -->
      </div>
    </main>
    <!-- END Page Content -->
  </div>
  <!-- END Page Container -->
  <!-- END Pages: Sign In: Boxed -->
</template>
