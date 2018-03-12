
<script>
  import Vue from 'Vue'

  const STATUS_RUNNING = 0;
  const STATUS_IDLE = 0;
  const STATUS_SUCCESS = 0;
  Vue.component('AnswerCard',Vue.extend(
    {
      template:'  <div class="container">\n' +
      '    <div class="card">\n' +
      '      <header class="card-header">\n' +
      '        <p class="card-header-title">\n' +
      '          <strong>刷题</strong><span class="tag" v-bind:class="answerLabel">{{answerStatusText}}</span>\n' +
      '        </p>\n' +
      '      </header>\n' +
      '      <div class="card-content">\n' +
      '        <div class="columns">\n' +
      '          <div class="column is-2">\n' +
      '            <p class="title">进度</p>\n' +
      '          </div>\n' +
      '          <div class="column is-7">\n' +
      '            <progress style="margin-top:10px;margin-left: 10px; margin-right: 10px" class="progress is-primary"\n' +
      '                      :value="answerPercent" max="100">\n' +
      '            </progress>\n' +
      '          </div>\n' +
      '          <div class="column is-3">\n' +
      '            <p class="title">{{answerPercent}}%完成</p>\n' +
      '          </div>\n' +
      '        </div>\n' +
      '\n' +
      '        <div class="columns">\n' +
      '          <div class="column is-2">\n' +
      '            <p style="margin-top: 12px" class="title">操作</p>\n' +
      '          </div>\n' +
      '\n' +
      '          <div class="column">\n' +
      '            <a @click="startAnswer(20)" :disabled="disableStart20" class="button is-warning is-large" style="margin-top: 5px">开始20%</a>\n' +
      '            <a @click="startAnswer(50)" :disabled="disableStart50" class="button is-warning is-large" style="margin-top: 5px">开始50%</a>\n' +
      '            <a @click="startAnswer(100)" :disabled="disableStart100" class="button is-warning is-large" style="margin-top: 5px">开始100%</a>\n' +
      '            <a @click="startAnswer(0)"  class="button is-warning is-large" style="margin-top: 5px">开始剩下全部</a>\n' +
      '          </div>\n' +
      '\n' +
      '        </div>\n' +
      '\n' +
      '\n' +
      '      </div>\n' +
      '\n' +
      '\n' +
      '    </div>\n' +
      '\n' +
      '    <div class="card">\n' +
      '      <header class="card-header">\n' +
      '        <p class="card-header-title">日志</p>\n' +
      '      </header>\n' +
      '      <div style="height: 300px; overflow: scroll">\n' +
      '\n' +
      '        <table class="table is-bordered is-striped is-narrow is-hoverable is-fullwidth">\n' +
      '          <thead>\n' +
      '          <tr>\n' +
      '            <th><abbr title="发生的时间">时间</abbr></th>\n' +
      '            <th><abbr title="日志内容">内容</abbr></th>\n' +
      '            <th><abbr title="当时的百分比">进度</abbr></th>\n' +
      '          </tr>\n' +
      '          </thead>\n' +
      '\n' +
      '          <tbody>\n' +
      '          <tr v-for="log in logs">\n' +
      '            <th>{{log.time}}</th>\n' +
      '            <td>{{log.content}}</td>\n' +
      '            <td>{{log.percent}}</td>\n' +
      '          </tr>\n' +
      '          </tbody>\n' +
      '\n' +
      '        </table>\n' +
      '      </div>\n' +
      '    </div>\n' +
      '    <br>\n' +
      '  </div>',
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
    )

  )</script>
