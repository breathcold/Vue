<template>
    <div>
        <h2>{{msg}}</h2>
        <hr/>
        <h3>{{count}}</h3>
        <div>
            <button @click="add(10)">+</button>
            <button @click="reduce">-</button>
        </div>
        <div>
            <button @click="addAction">+</button>
            <button @click="reduceAction">-</button>
        </div>
    </div>
</template>
<script>
    import store from '@/vuex/store'
    import {mapState,mapMutations,mapGetters,mapActions} from 'vuex'

    export default{
        data(){
            return{
                msg:'Hello Vuex'
            }
        },
        computed:{
            ...mapState(['count']),
            ...mapGetters(['count'])
        },
        methods:{
            ...mapMutations(['add','reduce']),
            ...mapActions(['addAction','reduceAction'])
        },
        store
        
    }
</script>