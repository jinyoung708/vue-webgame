<template>
  <td @click="onClickTd">{{cellData}}</td>
</template>

<script>
import EventBus from './EventBus';
export default {
    props: {
        cellData: String,
        rowIndex: Number,
        cellIndex: Number,
    },
    methods: {
        onClickTd() {
            if (this.cellData) return;
            const rootData = this.$root.$data;
            // console.log(this.$root.$data); // 최상위 데이터
            // console.log(this.$parent.$data); // 부모 데이터
            EventBus.$emit('clickTd', this.rowIndex, this.cellIndex);


            
        }
    },
}
</script>

<style>

</style>