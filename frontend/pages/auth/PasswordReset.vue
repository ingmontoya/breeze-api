<script setup></script>

<template>
  <!-- Pages: Password Reset: Boxed -->
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
        <!-- Password Reset Section -->
        <section class="w-full max-w-xl py-6">
          <!-- Header -->
          <header class="mb-10 text-center">
            <img
              src="/images/logo.png"
              alt="Logo"
              class="w-28 mx-auto mb-4" />
          </header>
          <!-- END Header -->

          <!-- Password Reset Form -->
          <div
            class="flex flex-col overflow-hidden rounded-lg bg-white shadow-sm dark:bg-gray-800 dark:text-gray-100"
          >
            <div class="grow p-5 md:px-16 md:py-12">
              <form class="space-y-6">
                <div class="space-y-1">
                  <label for="email" class="text-sm font-medium">Correo electrónico</label>
                  <input
                    type="email"
                    id="email"
                    name="email"
                    class="block w-full rounded-lg border border-gray-200 px-5 py-3 leading-6 placeholder-gray-500 focus:border-blue-500 focus:ring focus:ring-blue-500/50 dark:border-gray-600 dark:bg-gray-800 dark:placeholder-gray-400 dark:focus:border-blue-500"
                  />
                </div>
                <div>
                  <button
                    type="submit"
                    class="inline-flex w-full items-center justify-center gap-2 rounded-lg border border-blue-700 bg-blue-700 px-6 py-3 font-semibold leading-6 text-white hover:border-blue-600 hover:bg-blue-600 hover:text-white focus:ring focus:ring-blue-400/50 active:border-blue-700 active:bg-blue-700 dark:focus:ring-blue-400/90"
                  >
                    <span>Resetear Contraseña</span>
                  </button>
                </div>
              </form>
            </div>
            <div
              class="grow bg-gray-50 p-5 text-center text-sm md:px-16 dark:bg-gray-700/50"
            >
              <NuxtLink
                to="/"
                class="font-medium text-blue-600 hover:text-blue-400 dark:text-blue-400 dark:hover:text-blue-300"
                >Regresar al Login
              </NuxtLink>
            </div>
          </div>
          <!-- END Password Reset Form -->

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
        <!-- END Password Reset Section -->
      </div>
    </main>
    <!-- END Page Content -->
  </div>
  <!-- END Page Container -->
  <!-- END Pages: Password Reset: Boxed -->
</template>
