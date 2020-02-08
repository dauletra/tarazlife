<template>
    <div>
        <BlockHeader>Работа</BlockHeader>
        <div class="ml-3 mb-2 pb-3" v-for="job in jobs" v-bind:key="job.id">
                <span class="">
                    {{job.title}}
                </span>
            <span class="text-nowrap text-muted" style="font-size: .88rem">
                    {{job.description}}
                </span>
        </div>
    </div>
</template>

<script>
    import BlockHeader from '@/components/BlockHeader.vue'

    export default {
        name: "JobsBlock",
        props: {
            jobs: Array
        },
        components: {
            BlockHeader
        }
    }
</script>

<style scoped>

</style>
