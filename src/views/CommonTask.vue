<template>
  <div>
    <div>
      <div v-for="weekItem in list" :key="weekItem.week">
        <div class="week">{{weekItem.week}}孕周</div>
        <TaskItem :children="weekItem.children"/>
      </div>
    </div>
  </div>
</template>

<script>
import TaskItem from '../components/TaskItem'
export default {
  name: 'commonTask',
  components: { TaskItem },
  data () {
    return {
      list: [{
        week: '15',
        children: [{
          id: 0,
          title: '给宝宝唱儿歌',
          time: '2019.03.06',
          status: 0 // 0 已过期   1 已完成   2进行中
        }]
      }, {
        week: '16',
        children: [{
          id: 1,
          title: '给宝宝讲故事',
          time: '2019.02.22',
          status: 1 // 0 已过期   1 已完成   2进行中
        }, {
          id: 2,
          title: '注意口腔卫生',
          time: '2019.02.22',
          status: 2 // 0 已过期   1 已完成   2进行中
        }]
      }]
    }
  }

}
</script>

<style>
  .week {
    width: 43px;
    white-space: nowrap;
    margin-left: 21px;
    margin-top: 16px;
    margin-bottom: 6.5px;
    font-family: PingFangSC-Medium;
    font-size: 14px;
    font-weight: bold;
    color: #333;
  }

  .things {
    width: 335px;
    height: 79px;
    margin-left: 21px;
    margin-right: 19px;
    background: #FFF;
    box-shadow: 0 3px 10px 0 rgba(106, 106, 106, 0.10);
    border-radius: 6px;
    border-radius: 6px;
  }

  .task {
    position: relative;
    text-align: left;
    font-size: 16px;
    color: #666;
    margin-top: 14px;
    margin-left: 20px;
    margin-bottom: 9px;
  }

  .time {
    text-align: left;
    font-size: 13px;
    color: #999;
    margin-left: 20px;
    margin-bottom: 16px;
  }

  .left {
    float: left;
    width: 100%-148px;

  }

  .right {
    float: right;
    width: 78px;
  }

  .border-5e9bf8 {
    width: 64px;
    height: 20px;
    border: 0.5px solid #5E9BF8;
    border-radius: 11.5px;
    border-radius: 11.5px;
  }

  .viewdetail {
    float: left;
    font-size: 12px;
    color: #5394F8;
    text-align: center;
    line-height: 20px;
  }

  .triangle {
    float: right;
    width: 45px;
    height: 45px;

  }
</style>
