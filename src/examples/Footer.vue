<template>
  <footer class="py-3 footer">
    <div class="container-fluid">
      <div class="row align-items-center justify-content-lg-between">
        <div class="mb-4 col-lg-6 mb-lg-0">
          <div
            class="text-sm text-center copyright text-muted"
            :class="$store.state.isRTL ? 'text-lg-end' : 'text-lg-start'"
          >
            ©
            {{ new Date().getFullYear() }},
            <a
              href="https://www.ringonservice.com/"
              class="font-weight-bold"
              target="_blank"
            >
              ETECH SYSTEM
            </a>
            All Rights Reserved.
          </div>
        </div>
        <div class="col-lg-6">
        </div>
      </div>
    </div>
  </footer>
</template>

<script>
export default {
  name: "app-footer",
};
</script>
