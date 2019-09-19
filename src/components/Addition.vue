<template>
    <div>
        <!-- <h3>当前最新的count值为: {{$store.state.count}}</h3> -->
        <h3>{{$store.getters.showNum}}</h3>
        <button @click="handle1">+1</button>
        <button @click="handle2">+N</button>
        <button @click="handle3">+1 Async</button>
        <button @click="handle4">+N Async</button>
    </div>
</template>

<script>
export default {
    data() {
        return {}
    },
    methods: {
        handle1() {
            // commit的作用就是调用某个mutation的函数
            this.$store.commit('add')
        },
        handle2() {
            this.$store.commit('addN', 3)
        },
        // 异步的让count自增1
        handle3() {
            // dispatch函数专门用来触发action
            this.$store.dispatch('addAsync')
        },
        handle4() {
            this.$store.dispatch('addNAsync', 2)
        }
    }
}
</script>