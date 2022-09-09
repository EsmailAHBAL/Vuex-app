<template>
    <section class="container" style="margin: 5%;">
         <div class="box">
            <div class="block" style="display: flex;">
               <strong>Your Id => </strong> <p class="tag is-info" style="margin-left: 10px;"> {{user[0].id}}</p> 
            </div>
            <hr />
            <div class="block" style="display: flex;">
               <strong>Welcome => </strong> <p class="tag is-info" style="margin-left: 10px;"> {{user[0].username}}</p> 
            </div>
            <hr />
            <div class="block" style="display: flex;">
               <strong>Email =></strong> <p class="tag is-info" style="margin-left: 10px;"> {{user[0].email}}</p> 
            </div>
            <hr />
            <div class="block" style="display: flex;">
               <strong>Phone => </strong> <p class="tag is-info" style="margin-left: 10px;"> {{user[0].phone}}</p> 
            </div>
            <hr />
            <div class="block">
                <button class="button is-link" @click="BackTo()">Return 👈 </button>
            </div>
         </div>
    </section>
</template>

<script>
import { mapState } from 'vuex'
    export default{
        computed:{
            
            ...mapState(['userId','users']),
            user(){
                return this.users.filter(item=>{
                    if(item.id ==this.userId)
                    {
                        return item
                    }
                })
            }
        },
        methods:{
            BackTo(){
                this.$store.commit('BackTo')
            }
        }
    }
</script>