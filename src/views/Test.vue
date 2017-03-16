<template>
    <div>
        <vPower :result="result" @on-result-change="onResultChange"></vPower>
        <button @click="change">开关</button>
    </div>
</template>

<script>
    export default {
        data() {
            return {
                result: false
            }
        },
        methods: {
            change() {
                this.result = !this.result
            },
            onResultChange(val){
                this.result = val
            }
        }
    }
</script>