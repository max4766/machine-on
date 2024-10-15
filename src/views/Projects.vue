<template>
    <div class="py-4 container-fluid">
        <div class="row mb-4">
            <div class="col-lg-12 position-relative z-index-2">
            <div class="row">
                <div class="col-2" v-for="(item, index) in items" :key="index">
                    <DefaultInfoCard
                        :icon="item.icon"
                        :title="item.title"
                        :description="item.description"
                        :value="item.value"
                        :text="item.text"
                    />
                </div>
            </div>
            <div class="row mt-4">
                <div class="col-3">
                    <span>hi</span>
                </div>
                <div class="col-3">
                    <span>hi</span>
                </div>
                <div class="col-3">
                    <span>hi</span>
                </div>
                <div class="col-3">
                    <span>hi</span>
                </div>
            </div>
            <div class="row mt-4">
                <div class="col-3">
                    <span>hi</span>
                </div>
                <div class="col-3">
                    <span>hi</span>
                </div>
                <div class="col-3">
                    <span>hi</span>
                </div>
                <div class="col-3">
                    <span>hi</span>
                </div>
            </div>
        </div>
    </div>

    <div class="row">
      <div class="col-4">
        <span>hi</span>
      </div>
      <div class="col-4">
        <span>hi</span>
      </div>
      <div class="col-4">
        <span>hi</span>
      </div>
    </div>

    <div class="row">
      <div class="col-8">
        <span>hi</span>
      </div>
      <div class="col-4">
        <span>hi</span>
      </div>
    </div>

  </div>
</template>

<script>
    import DefaultInfoCard from "@/examples/Cards/DefaultInfoCard.vue"

    export default {
        name: 'Projects',
        data() {
            return {
                items: [
                    {
                        icon: {
                            component: 'monitor',
                            background: 'bg-primary',
                        },
                        title: 'Host',
                        description: 'Updated 2024-10-15',
                        value: 3,
                        text: 'text-primary'
                    },
                    {
                        icon: {
                            component: 'build',
                            background: 'bg-secondary',
                        },
                        title: 'CPU',
                        description: 'Updated 2024-10-14',
                        value: 144 + 'Cores',
                        text: 'text-secondary'
                    },
                    {
                        icon: {
                            component: 'man',
                            background: 'bg-warning',
                        },
                        title: 'Memory',
                        description: 'Updated 2024-10-13',
                        value: 1.48 + 'TB',
                        text: 'text-warning'
                    },
                    {
                        icon: {
                            component: 'woman',
                            background: 'bg-info',
                        },
                        title: 'Storage',
                        description: 'Updated 2024-10-12',
                        value: 4 + 'TB',
                        text: 'text-info'
                    },
                    {
                        icon: {
                            component: 'warning',
                            background: 'bg-danger',
                        },
                        title: 'Cluster',
                        description: 'Updated 2024-10-11',
                        value: 1,
                        text: 'text-danger'
                    },
                    {
                        icon: {
                            component: 'face',
                            background: 'bg-dark',
                        },
                        title: 'Data Center',
                        description: 'Updated 2024-10-10',
                        value: 1,
                        text: 'text-dark'
                    },
                ],
            }
        },
        components: {
            DefaultInfoCard
        }, 
    }
</script>