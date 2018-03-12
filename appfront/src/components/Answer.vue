<template>
  <div class="container">
    <div class="card">
      <header class="card-header">
        <p class="card-header-title">
          <strong>刷题</strong><span class="tag" v-bind:class="answerLabel">{{answerStatusText}}</span>
        </p>
      </header>
      <div class="card-content">
        <div class="columns">
          <div class="column is-2">
            <p class="title">进度</p>
          </div>
          <div class="column is-7">
            <progress style="margin-top:10px;margin-left: 10px; margin-right: 10px" class="progress is-primary"
                      :value="answerPercent" max="100">
            </progress>
          </div>
          <div class="column is-3">
            <p class="title">{{answerPercent}}%完成</p>
          </div>
        </div>

        <div class="columns">
          <div class="column is-2">
            <p style="margin-top: 12px" class="title">操作</p>
          </div>

          <div class="column">
            <a @click="startAnswer(20)" :disabled="disableStart20" class="button is-warning is-large" style="margin-top: 5px">开始20%</a>
            <a @click="startAnswer(50)" :disabled="disableStart50" class="button is-warning is-large" style="margin-top: 5px">开始50%</a>
            <a @click="startAnswer(100)" :disabled="disableStart100" class="button is-warning is-large" style="margin-top: 5px">开始100%</a>
            <a @click="startAnswer(0)"  class="button is-warning is-large" style="margin-top: 5px">开始剩下全部</a>
          </div>

        </div>


      </div>


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

          <tbody>
          <tr v-for="log in logs">
            <th>{{log.time}}</th>
            <td>{{log.content}}</td>
            <td>{{log.percent}}</td>
          </tr>
          </tbody>

        </table>
      </div>
    </div>
    <br>
  </div>
</template>

<script>
  import Vue from 'Vue'

  const STATUS_RUNNING = 0;
  const STATUS_IDLE = 0;
  const STATUS_SUCCESS = 0;
  export default {
    name: 'answerCard',
    data() {
      return {
        logs: [
          {
            time: '2018-02-02',
            content: '第24页完成 分数89',
            percent: '38',
          },
        ],
        answerPercent: 50,
        answerStatusText: '空闲中',
        answerLabel: 'is-light',

        disableStart20:true,
        disableStart50:false,
        disableStart100:false,
      }
    },
    methods: {
      setStatus: function (status) {
        switch (status) {
          case STATUS_RUNNING:
            this.answerStatusText = '进行中';
            this.answerLabel = 'is-dark';
            break;
          case STATUS_SUCCESS:
            this.answerStatusText = '已完成';
            this.answerLabel = 'is-success';
            break;
          case STATUS_IDLE:
            this.answerStatusText = '空闲中';
            this.answerLabel = 'is-light';
            break;
        }
      },
      startAnswer:function (percent) {
        switch (percent){

        }
      },

      setDisabled(answerLeft){
        if(answerLeft<0||answerLeft>100){
          error
        }else {
          if(answerLeft>50){
            this.disableStart100 = true;
          }
          else if(answerLeft<=50 && answerLeft >20){
            this.disableStart50 = true;
            this.disableStart100 = true;
          }
          else if(answerLeft<=20){
            this.disableStart20 = true;
            this.disableStart50 = true;
            this.disableStart100 = true;

          }

        }
      }
    }
  }
</script>
