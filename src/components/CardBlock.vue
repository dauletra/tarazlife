<template>
    <div class="bg-white" style="">
        <BlockHeader>{{title}}</BlockHeader>
        <div class="mb-3 d-flex hide-scroll-bar">
            <div class="p-1 p-md-2 ml-3 mr-md-3 rounded text-nowrap" style="background-color: #e6e6e6" v-for="category in categories" v-bind:key="category.id">{{category.name}}</div>
        </div>

        <div class="d-flex hide-scroll-bar shadow-only-right" style="">
            <div class="ml-3 mr-md-3 border rounded" style="width: 201px; min-width: 201px;" v-for="organization in organizations" v-bind:key="organization.id">
                <div class="p-1 text-center text-nowrap overflow-hidden" style="text-overflow: ellipsis;">{{organization.title}}</div>
                <div style="height: 100px; max-height: 100px">
                    <img v-bind:src="organization.img" alt="" class="img-fluid" />
                </div>
                <div class="px-2 pt-1 hide-scroll-bar" style="height: 72px; overflow-y: auto; font-size: .85rem">
                    {{organization.text}}
                </div>
                <div class="px-1 py-1 text-center overflow-hidden border-top" style="text-overflow: ellipsis;">{{organization.footer}}</div>
            </div>
        </div>
    </div>
</template>

<script>
    import BlockHeader from '@/components/BlockHeader.vue'

    export default {
        name: "CardBlock",
        props: {
            title: String,
            categories: Array,
            organizations: Array
        },
        data() {
            return {

            }
        },
        components: {
            BlockHeader
        }
    }
</script>

<style scoped>
    .shadow-left-right {
        box-shadow: inset 25px 0 15px -25px rgba(0,0,0,0.45), inset -25px 0 15px -25px rgba(0,0,0,0.45);
    }
    .shadow-only-left {
        box-shadow: inset 25px 0 15px -25px rgba(0,0,0,0.45)
    }
    .shadow-only-right {
        box-shadow: inset -25px 0 15px -25px rgba(0,0,0,0.45);
    }
</style>
