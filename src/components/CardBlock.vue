<template>
    <div class="" style="">
        <div class="mb-3 h5 font-weight-bold">{{title}}</div>
        <div class="mb-3 d-flex hide-scroll-bar">
            <div class="p-1 p-md-2 mx-2 rounded text-nowrap" style="background-color: #e6e6e6" v-for="category in categories" v-bind:key="category.id">{{category.name}}</div>
        </div>

        <div class="d-flex hide-scroll-bar shadow-only-right" style="">
            <div class="mr-4 border rounded" style="width: 200px; min-width: 200px;" v-for="organization in organizations" v-bind:key="organization.id">
                <div class="px-1 py-1 text-center text-nowrap overflow-hidden" style="text-overflow: ellipsis;">{{organization.title}}</div>
                <div style="height: 100px; max-height: 100px">
                    <img v-bind:src="organization.img" alt="" class="img-fluid" />
                </div>
                <div class="px-1 hide-scroll-bar" style="height: 72px; overflow-y: auto; font-size: .85rem">
                    {{organization.text}}
                </div>
                <div class="px-1 py-1 text-center overflow-hidden" style="text-overflow: ellipsis;">{{organization.footer}}</div>
            </div>
        </div>
    </div>
</template>

<script>
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
