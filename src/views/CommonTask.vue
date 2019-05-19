<template>
  <div>
    <div>
      <div v-for="weekItem in list" :key="weekItem.week">
        <div class="week">{{weekItem.week}}孕周</div>
        <div class="things" v-for="item in weekItem.children" :key="item.id">
          <div class="left">
            <p class="task">{{item.title}}</p>
            <p class="time">{{showSubTitle(item)}}</p>
          </div>
          <div class="right">
            <div class="border-5e9bf8"><p class="viewdetail">查看详情</p></div>
            <div class="triangle"><p>{{statusLabelMaps[item.status]}}</p></div>
          </div>
      </div>
      </div>
      <!-- <div>
          <div class="week">16孕周（当前）</div>
          <div class="things">
            <div class="left">
                <p class="task">给宝宝讲故事</p>
                <p class="time">完成时间：2019.02.22</p>
            </div>
            <div class="right">
              <div><p>去完成</p></div>
              <div><p>已完成</p></div>
            </div>
            <div class="left">
                <p class="task">注意个人口腔卫生</p>
                <p class="time">进行中</p>
            </div>
            <div class="right">
              <div><p>查看详情</p></div>
              <div><p>进行中</p></div>
            </div>
            <div class="left">
                <p class="task">排查ABO溶血</p>
                <p class="time">进行中</p>
            </div>
            <div class="right">
                <div><p>查看详情</p></div>
                <div><p>进行中</p></div>
            </div>
          </div>
        </div>
        <div>
            <div class="week">17孕周</div>
            <div class="things">
              <div class="left">
                  <p class="task">适当的补充锌元素</p>
                  <p class="time">即将开始：2019.02.26</p>
              </div>
              <div class="right">
                <div><p>查看详情</p></div>
                <div><p>未开始</p></div>
              </div>
              <div class="left">
                  <p class="task">多呼吸新鲜空气</p>
                  <p class="time">即将开始：2019.08.26</p>
              </div>
              <div class="right">
                  <div><p>查看详情</p></div>
                  <div><p>未开始</p></div>
              </div>
            </div>
          </div> -->
    </div>
  </div>
</template>

<script>
export default {
  name: 'commonTask',
  data () {
    return {
      statusLabelMaps: {
        0: '已过期',
        1: '已完成',
        2: '进行中'
      },
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
  *{
    margin: 0;
    padding: 0;
  }
  body{
    background: #F8F8F8;
  }
  .week{
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
