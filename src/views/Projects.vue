<template>
    <div class="py-4 container-fluid">
        <div class="row mb-4">
            <div class="col-lg-12 position-relative z-index-2">
                
                <div class="row">
                    <div class="col-2" v-for="(item, index) in defaultInfoCardItems" :key="index">
                        <DefaultInfoCard
                            :icon="item.icon"
                            :title="item.title"
                            :description="item.description"
                            :value="item.value"
                            :text="item.text"
                        />
                    </div>
                </div>
                
                <div class="row mt-2">
                    <div class="col-3 mt-4" v-for="(item, index) in miniStatisticsCardItems" :key="index">
                        <mini-statistics-card
                            :title="item.title"
                            :detail="item.detail"
                            :icon="item.icon"
                        />
                </div>

            </div>
        </div>
    </div>

    <div class="row">
        <div class="col-6 mt-3">
            <chart-holder-card
                title="Operation System"
                update="campaign sent 2 days ago"
                color="info"
            >
                <reports-bar-chart
                :chart="{
                    labels: ['M', 'T', 'W', 'T', 'F', 'S', 'S'],
                    datasets: {
                        label: 'Sales',
                        data: [50, 20, 10, 22, 50, 10, 40],
                    },
                }"
                />
            </chart-holder-card>
            </div>
            <div class="col-6 mt-3">
            <chart-holder-card
                title="Monthly VM Counts Change"
                update="updated 4 min ago"
                color="info"
            >
                <reports-line-chart
                    :chart="{
                        labels: [
                        'Apr',
                        'May',
                        'Jun',
                        'Jul',
                        'Aug',
                        'Sep',
                        'Oct',
                        'Nov',
                        'Dec',
                        ],
                        datasets: {
                            label: 'Mobile apps',
                            data: [50, 40, 300, 320, 500, 350, 200, 230, 500],
                        },
                    }"
                />
        </chart-holder-card>
        </div>
    </div>

  </div>
</template>

<script>
    import DefaultInfoCard from "@/examples/Cards/DefaultInfoCard.vue";
    import MiniStatisticsCard from "./components/MiniStatisticsCard.vue";
    import ChartHolderCard from "./components/ChartHolderCard.vue";
    import ReportsBarChart from "@/examples/Charts/ReportsBarChart.vue";
    import ReportsLineChart from "@/examples/Charts/ReportsLineChart.vue";

    export default {
        name: 'Projects',
        data() {
            return {
                defaultInfoCardItems: [
                    {
                        icon: {
                            component: 'monitor',
                            background: 'bg-gradient-secondary',
                        },
                        title: 'Host',
                        description: 'Updated 2024-10-15',
                        value: 3,
                        text: 'text-dark'
                    },
                    {
                        icon: {
                            component: 'build',
                            background: 'bg-gradient-secondary',
                        },
                        title: 'CPU',
                        description: 'Updated 2024-10-14',
                        value: '144 Cores',
                        text: 'text-dark'
                    },
                    {
                        icon: {
                            component: 'man',
                            background: 'bg-gradient-secondary',
                        },
                        title: 'Memory',
                        description: 'Updated 2024-10-13',
                        value: '1.48 TB',
                        text: 'text-dark'
                    },
                    {
                        icon: {
                            component: 'woman',
                            background: 'bg-gradient-secondary',
                        },
                        title: 'Storage',
                        description: 'Updated 2024-10-12',
                        value: '4 TB',
                        text: 'text-dark'
                    },
                    {
                        icon: {
                            component: 'warning',
                            background: 'bg-gradient-secondary',
                        },
                        title: 'Cluster',
                        description: 'Updated 2024-10-11',
                        value: 1,
                        text: 'text-dark'
                    },
                    {
                        icon: {
                            component: 'face',
                            background: 'bg-gradient-secondary',
                        },
                        title: 'Data Center',
                        description: 'Updated 2024-10-10',
                        value: 1,
                        text: 'text-dark'
                    },
                ],
                miniStatisticsCardItems: [
                    {
                        title: {
                            text: 'Virtual Machine',
                            value: 109,
                        },
                        detail: "<span class='text-danger text-sm font-weight-bolder'>-2%</span> than last week",
                        icon: {
                            name: 'weekend',
                            color: 'text-white',
                            background: 'danger',
                        },
                    },
                    {
                        title: {
                            text: 'Allocated CPU',
                            value: '555 vCPU',
                        },
                        detail: "<span class='text-secondary text-sm font-weight-bolder'>0%</span> than last week",
                        icon: {
                            name: 'weekend',
                            color: 'text-white',
                            background: 'secondary',
                        },
                    },
                    {
                        title: {
                            text: 'Allocated Memory',
                            value: '1.6 TB',
                        },
                        detail: "<span class='text-success text-sm font-weight-bolder'>+55%</span> than last week",
                        icon: {
                            name: 'weekend',
                            color: 'text-white',
                            background: 'success',
                        },
                    },
                    {
                        title: {
                            text: 'Project',
                            value: 0,
                        },
                        detail: "<span class='text-secondary text-sm font-weight-bolder'>0%</span> than last week",
                        icon: {
                            name: 'weekend',
                            color: 'text-white',
                            background: 'secondary',
                        },
                    },
                    {
                        title: {
                            text: 'Totall Cost',
                            value: '₩ 7,263,413.5',
                        },
                        detail: "<span class='text-success text-sm font-weight-bolder'>+0.05%</span> than last week",
                        icon: {
                            name: 'weekend',
                            color: 'text-white',
                            background: 'success',
                        },
                    },
                    {
                        title: {
                            text: 'Data Store Cost',
                            value: '₩ 1,741,925.87',
                        },
                        detail: "<span class='text-secondary text-sm font-weight-bolder'>0%</span> than last week",
                        icon: {
                            name: 'weekend',
                            color: 'text-white',
                            background: 'secondary',
                        },
                    },
                    {
                        title: {
                            text: 'Potential Cost Save',
                            value: '₩ 1,974,215.04',
                        },
                        detail: "<span class='text-danger text-sm font-weight-bolder'>-0.01%</span> than last week",
                        icon: {
                            name: 'weekend',
                            color: 'text-white',
                            background: 'danger',
                        },
                    },
                    {
                        title: {
                            text: 'Actual Cost Save',
                            value: 0,
                        },
                        detail: "<span class='text-secondary text-sm font-weight-bolder'>0%</span> than last week",
                        icon: {
                            name: 'weekend',
                            color: 'text-white',
                            background: 'secondary',
                        },
                    },
                ]
            }
        },
        components: {
            DefaultInfoCard,
            MiniStatisticsCard,
            ChartHolderCard,
            ReportsBarChart,
            ReportsLineChart,
        },
    }
</script>