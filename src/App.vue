<template>
    <div>
        <div>
            直接一次加载完成

            <el-scrollbar>
                <div class="flex-content">
                    <p class="item" v-for="item in 50" :key="item">{{ item }}</p>
                </div>
            </el-scrollbar>
        </div>
        <div>
            动态加载，<br />
            <el-button @click="add">添加元素</el-button>
            <el-button @click="del">删除元素</el-button>
            <el-scrollbar wrap-style="width:650px;">
                <div class="flex-content">
                    <p class="item" v-for="item in count" :key="item">{{ item }}</p>
                </div>
            </el-scrollbar>
        </div>
    </div>
</template>

<script>
export default {
    data() {
        return {
            count: 3
        }
    },
    methods: {
        add() {
            this.count++
        },
        del() {
            if (this.count > 0) {
                this.count--
            }
        }
    }
}
</script>

<style scoped>
.el-scrollbar {
    width: 800px;
    background-color: #fef0f0;
}
.flex-content {
    width: 500px;
    display: flex;
    background-color: #fef;
}
.flex-content .item {
    flex-shrink: 0;
    width: 100px;
    height: 50px;
    margin: 10px;
    border-radius: 4px;
    background: rgb(216, 208, 208);
    color: #f56c6c;
}
</style>
