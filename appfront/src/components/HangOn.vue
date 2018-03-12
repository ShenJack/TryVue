<template>
  <div class="container">
    <div class="card">
      <header class="card-header">
        <p class="card-header-title">
          挂机<span class="tag is-dark">{{hangOnStatus}}</span>
        </p>
      </header>
      <div class="card-content">
        <div class="columns">
          <div class="column is-2">
            <p class="title">进度</p>
          </div>
          <div class="column is-7">
            <progress style="margin-top:10px;margin-left: 10px; margin-right: 10px" class="progress is-primary"
                      :value="hangOnPercent" max="100">
            </progress>
          </div>
          <div class="column is-3">
            <p class="title">{{hangOnMinutes}}/{{totalMinutes}}分钟</p>
          </div>
        </div>

        <div class="columns">
          <div class="column is-2">
            <p style="margin-top: 12px" class="title">操作</p>
          </div>

          <div class="column">
            <a id="start20" class="button is-warning is-large" style="margin-top: 5px">开始20%</a>
            <a id="start50" class="button is-warning is-large" style="margin-top: 5px">开始50%</a>
            <a id="start100" class="button is-warning is-large" style="margin-top: 5px">开始100%</a>
            <a id="startLeft" class="button is-warning is-large" style="margin-top: 5px">开始剩下全部</a>
          </div>

        </div>
      </div>
      Hang On Card
    </div>
    <div class="card">
      <header class="card-header">
        <p class="card-header-title">日志</p>
      </header>
      <div style="height: 300px; overflow: scroll">

        <table class="table is-bordered is-striped is-narrow is-hoverable is-fullwidth">
          <thead>
          <tr>
            <th><abbr title="发生的时间">时间</abbr></th>
            <th><abbr title="日志内容">内容</abbr></th>
            <th><abbr title="当时的百分比">进度</abbr></th>
          </tr>
          </thead>

          <tbody >
            <tr v-for="log in logs">
              <th>{{log.time}}</th>
              <td>{{log.content}}</td>
              <td>{{log.percent}}</td>
            </tr>
          </tbody>
        </table>
      </div>
    </div>
  </div>
</template>

<script>
  export default {
    name: 'hangOn',
    data() {
      return {
        hangOnStatus: '空闲中',
        hangOnPercent: 80,
        hangOnMinutes:670,
        totalMinutes:800,
        logs:[
          {
            time:'2018-02-02',
            content:'第24页完成 分数89',
            percent:'38',
          },
        ]
      }
    }
  }
</script>
