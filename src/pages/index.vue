<template>
  <v-layout>
    <v-app-bar color="transparent" flat>
      <template #prepend>
        <v-app-bar-nav-icon
          v-if="$vuetify.display.smAndDown"
          @click="drawer = !drawer"
        />
      </template>

      <div class="d-flex flex-1-1-0 ps-md-4">
        <v-avatar image="@/assets/logo-basic.png" rounded="0" />
      </div>

      <div class="d-md-flex d-none ga-4 mx-auto">
        <v-btn class="text-none" text="项目列表" />
        <v-btn class="text-none" text="镜像站" />
        <v-btn class="text-none" text="状态监控" />
      </div>

      <div class="d-flex flex-1-1-0 pe-3">
        <v-btn class="ms-auto text-none" prepend-icon="mdi-github" slim text="GitHub" />
      </div>
    </v-app-bar>

    <v-main :min-height="$vuetify.display.mdAndUp ? 800 : 550">
      <v-container class="h-100 d-flex align-center justify-center">
        <div class="w-100 w-md-50 text-center">
          <v-chip border="thin opacity-25" color="surface" variant="flat">
            官网V2仍在开发中，敬请期待
          </v-chip>

          <h1 class="text-h4 text-md-h2 font-weight-bold my-6">
            RBQ Dev Projects
          </h1>

          <div class="text-body-1 text-medium-emphasis mb-10"></div>

          <div class="d-flex ga-4 justify-center">
            <v-btn
              class="text-none"
              color="primary"
              flat
              rounded="lg"
              text="Get started"
            />

            <v-btn
              append-icon="mdi-chevron-right"
              class="text-none"
              flat
              rounded="lg"
              text="Learn more"
            />
          </div>
        </div>

        <div class="v-bg position-absolute top-0 right-0 left-0 bottom-0">
          <div aria-hidden="true" class="overflow-hidden opacity-20 w-100 h-100" />
        </div>
      </v-container>
    </v-main>
  </v-layout>
</template>

<script lang="ts" setup>
  import { shallowRef } from 'vue'
  const drawer = shallowRef(false)
</script>

<style scoped>
.v-bg {
  filter: blur(56px);
  pointer-events: none;
}

.v-bg > div {
  background: linear-gradient(
    to bottom right,
    rgb(var(--v-theme-primary)),
    rgb(var(--v-theme-error))
  );
  z-index: -10;
  clip-path: polygon(20% 50%, 27% 66%, 41% 66%, 50% 50%, 41% 34%, 27% 34%, 20% 50%, 55% 50%, 62% 66%, 76% 66%, 85% 50%, 76% 34%, 62% 34%, 55% 50%, 30% 50%, 37% 66%, 51% 66%, 60% 50%, 51% 34%, 37% 34%, 30% 50%);
}
</style>
