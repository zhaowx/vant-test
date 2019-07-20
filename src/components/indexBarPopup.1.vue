<template>
    <div>
        <van-button type="primary" @click="showPopup">
            展示弹出层
        </van-button>

        <van-popup 
            v-model="show"
            position="right"
            :style="{ width: '100%', height:'100%', position: 'absolute' }">
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
        </van-popup>
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
        
    }
    form{
        z-index: 3;
    }
    .wrapper{
        overflow: auto;
    }
</style>