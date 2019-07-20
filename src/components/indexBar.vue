<template>
    <van-index-bar :index-list="indexList" :sticky="false" highlight-color="#2c3e50">
        

        <template v-for="(value, index) in data">
            <van-index-anchor :index="index">标题 {{index}}</van-index-anchor>
            <template v-for="item in value">
                <van-cell  :title="item.name"/>
            </template>
        </template>    
    </van-index-bar>
</template>

<script>

export default {
    name: 'indexBar',
    data() {
        return {
            indexList: [1, 2, 3, 4, 5, 6, 7, 8, 9, 10],
            data: {}
        }
    },
    mounted (){
        this.makeData();
    },
    methods: {
        makeData () {
            let data = {};
            for (let i=1; i < 11; i++){
                let temp = [];
                for(let j=0; j<100; j++){
                    temp.push({
                        name: 'item' + (i) + ' ---- '+ j
                    });
                }
                data[i] = temp;
            }
            this.data = data;
            console.log('data ====> ', data);
        }
    }
}
</script>

<style>
.van-index-bar{
    height: 100%;
    position: relative;
}
</style>