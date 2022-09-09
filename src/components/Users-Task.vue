<template>
    <div class="">
        <div class="columns is-multiline">

            <div class="column is-3" v-for="user in users" :key="user.id">
                <div class="card">
                    <div class="card=content" style="padding-top: 2%;">
                        <div class="block tocenter">
                            <span class="tag is-success">{{user.id}}</span>
                        </div>
                        <div class="container block" style="width: 50%;">
                            <progress class="progress is-small" value="100" max="100"></progress>
                        </div>
                        <div class="block tocenter">
                            <h3>Phone</h3>
                            <span class="tag is-succes" style="margin-left: 8px;">{{user.phone}}</span>
                        </div>

                        <div class="block tocenter">
                            <h3>username</h3>
                            <button class="button is-success" style="margin-left: 8px;">{{user.username}}</button>
                        </div>
                        <div class="block tocenter">

                            <button class="button is-info">{{user.email}}</button>
                        </div>
                        <div class="block tocenter">

                            <button class="button is-dark" @click="toNextPage(user.id)">To Next Page</button>
                        </div>
                        <br />
                    </div>
                </div>
                <hr />
            </div>

        </div>
    </div>
</template>
<script>
    import {
        mapState
    } from 'vuex'
    export default {
        computed: {
            ...mapState(['users'])

        },methods:{
            toNextPage(id){
                this.$store.commit("toNextPage",id)
            }
        }
    }
</script>

<style>
    .tocenter {
        display: flex;
        justify-content: center;
    }
</style>