<template>
  <div>
    <div class="things" v-for="item in children" :key="item.id">
      <div class="left">
        <p class="task">{{item.title}}</p>
        <p class="time">{{showSubTitle(item)}}</p>
      </div>
      <div class="right">
        <div class="border-5e9bf8">
          <p class="viewdetail">查看详情</p>
        </div>
        <div class="triangle">
          <p>{{statusLabelMaps[item.status]}}</p>
        </div>
      </div>
    </div>
  </div>

</template>

<script>
export default {
  name: 'TaskItem',
  props: ['children'],
  data () {
    return {
      statusLabelMaps: {
        0: '已过期',
        1: '已完成',
        2: '进行中'
      },
      weekItem: {
        children: {}
      }
    }
  },
  methods: {
    showSubTitle ({ status, time }) {
      if (status === 0) {
        return `过期时间${time}`
      } else if (status === 1) {
        return `完成时间${time}`
      } else if (status === 2) {
        return '进行中'
      }
      return ''
    }
  }
}
</script>

<style>
  .things{
    width: 335px;
    height: 79px;
    margin-left:21px;
    margin-right: 19px;
    background: #FFF;
    box-shadow: 0 3px 10px 0 rgba(106,106,106,0.10);
    border-radius: 6px;
    border-radius: 6px;
  }
  .task{
    position: relative;
    text-align: left;
    font-size: 16px;
    color: #666;
    margin-top: 14px;
    margin-left: 20px;
    margin-bottom: 9px;
  }
  .time{
    text-align: left;
    font-size: 13px;
    color: #999;
    margin-left: 20px;
    margin-bottom: 16px;
  }
  .left{
    float: left;
    width: 100%-148px;

  }
  .right{
    float: right;
    width: 78px;
  }
  .border-5e9bf8{
    width: 64px;
    height: 20px;
    border: 0.5px solid #5E9BF8;
    border-radius: 11.5px;
    border-radius: 11.5px;
  }
  .viewdetail{
    float:left;
    font-size: 12px;
    color: #5394F8;
    text-align: center;
    line-height: 20px;
  }
  .triangle{
    float:right;
    width: 45px;
    height: 45px;

  }

</style>
