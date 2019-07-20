<template>
    <div class="cont">
        <form action="/">
            <van-search
                v-model="value"
                placeholder="请输入搜索关键词"
                show-action
                @cancel="onCancel"
            />
        </form>
        <div class="wrapper">
            <index-bar />
        </div>
    </div>
</template>

<script>
import IndexBar from './indexBar.vue'

export default {
    name: 'indexBarPopup',
    components: {
        IndexBar
    },
    data() {
        return {
            show: false,
            value: ''
        }
    },
    mounted (){
    },
    methods: {
        showPopup() {
            this.show = true;
        },
        onCancel () {

        }
    }
}
</script>

<style>
    .cont{
        height: 100%;
        display: flex;
        flex-direction: column;
        position: absolute;
        top: 0;
        bottom: 0;
        left: 0;
        right: 0;
        background-color: #ffffff;
    }
    form{
        z-index: 3;
    }
    .wrapper{
        overflow: auto;

        -webkit-overflow-scrolling: touch;
    }
</style>