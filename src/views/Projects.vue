<template>
    <div class="py-4 container-fluid">
        <div class="row mb-4">
            <div class="col-lg-12 position-relative z-index-2">
                
                <div class="row">
                    <!-- Host, CPU, Memory, Storage, Cluster, DataCenter -->
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
                    <!-- VirtualMachine, AllocatedCPU, AllocatedMemory, Project, TotalCost, DataStoreCost, PotentialCostSave, ActualCostSave -->
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
            <!-- operation-system-chart -->
            <chart-holder-card
                title="Operation System"
                update="Updated 2 mintutes ago"
                color="primary"
            >
                <reports-bar-chart
                    id="operation-system-chart"
                    :chart="{
                        labels: [
                            'CentOS 7 (64-bit)',
                            'VMware ESXi 6.5 or later',
                            'Other 3.x or later Linux (64-bit)',
                            'Microsoft Windows Server 2019 (64-bit)',
                            'Ubuntu Linux (64-bit)',
                            'VMware ESXi 7.0 or later',
                            'Other 3.x Linux (64-bit)',
                            'Red Hat Enterprise Linux 9 (64-bit)'
                        ],
                        datasets: {
                            label: 'Counts',
                            data: [22, 3, 16, 8, 37, 11, 1, 2],
                        },
                    }"
                />
            </chart-holder-card>
        </div>
        <div class="col-6 mt-3">
            <div class="row">
                <div class="col-12">
                    <!-- monthly-vm-counts-change-chart -->
                    <chart-holder-card
                        title="Monthly VM Counts Change"
                        update="updated 6 min ago"
                        color="primary"
                    >
                        <reports-line-chart
                            id="monthly-vm-counts-change-chart"
                            :chart="{
                                labels: [
                                    '15',
                                    '16',
                                    '17',
                                    '18',
                                    '19',
                                    '20',
                                    '21',
                                    '22',
                                    '23',
                                    '24',
                                    '25',
                                    '26',
                                    '27',
                                    '28',
                                    '29',
                                    '30',
                                    '1',
                                    '2',
                                    '3',
                                    '4',
                                    '5',
                                    '6',
                                    '7',
                                    '8',
                                    '9',
                                    '10',
                                    '11',
                                    '12',
                                    '13',
                                    '14',
                                    '15',
                                ],
                                datasets: {
                                    label: 'Desktops',
                                    data: [
                                        97,
                                        97,
                                        97,
                                        97,
                                        101,
                                        101,
                                        101,
                                        101,
                                        102,
                                        105,
                                        105,
                                        105,
                                        105,
                                        106,
                                        106,
                                        106,
                                        107,
                                        107,
                                        107,
                                        108,
                                        108,
                                        108,
                                        109,
                                        109,
                                        109,
                                        109,
                                        109,
                                        109,
                                        109,
                                        109,
                                        109,
                                    ],
                                },
                            }"
                        />
                    </chart-holder-card>
                </div>
                <div class="col-6 mt-5">
                    <!-- vm-power-status-chart -->
                    <chart-holder-card
                        title="VM Power Status"
                        update="updated 4 min ago"
                        color="primary"
                    >
                        <reports-pie-chart
                            id="vm-power-status-chart"
                            :chart="{
                                labels: [
                                    'On',
                                    'Off',
                                ],
                                datasets: {
                                    data: [
                                        88,
                                        21,
                                    ],
                                },
                            }"
                        />
                    </chart-holder-card>
                </div>
                <div class="col-6 mt-5">
                    
                </div>
            </div>
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
    import ReportsPieChart from "@/examples/Charts/ReportsPieChart.vue";

    export default {
        name: 'Projects',
        data() {
            return {
                defaultInfoCardItems: [
                    {
                        icon: {
                            component: 'monitor',
                            background: 'bg-gradient-primary',
                        },
                        title: 'Host',
                        description: 'Updated 2024-10-15',
                        value: 3,
                        text: 'text-primary'
                    },
                    {
                        icon: {
                            component: 'build',
                            background: 'bg-gradient-primary',
                        },
                        title: 'CPU',
                        description: 'Updated 2024-10-14',
                        value: '144 Cores',
                        text: 'text-primary'
                    },
                    {
                        icon: {
                            component: 'man',
                            background: 'bg-gradient-primary',
                        },
                        title: 'Memory',
                        description: 'Updated 2024-10-13',
                        value: '1.48 TB',
                        text: 'text-primary'
                    },
                    {
                        icon: {
                            component: 'woman',
                            background: 'bg-gradient-primary',
                        },
                        title: 'Storage',
                        description: 'Updated 2024-10-12',
                        value: '4 TB',
                        text: 'text-primary'
                    },
                    {
                        icon: {
                            component: 'warning',
                            background: 'bg-gradient-primary',
                        },
                        title: 'Cluster',
                        description: 'Updated 2024-10-11',
                        value: 1,
                        text: 'text-primary'
                    },
                    {
                        icon: {
                            component: 'face',
                            background: 'bg-gradient-primary',
                        },
                        title: 'Data Center',
                        description: 'Updated 2024-10-10',
                        value: 1,
                        text: 'text-primary'
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
            ReportsPieChart,
        },
    }
</script>