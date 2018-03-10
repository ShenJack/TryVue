<template>
  <div class="container">
    <article class="media" style="margin-left: 50px;margin-right: 50px">
      <figure class="media-left">
        <p class="image is-128x128">
          <img src="http://img.zcool.cn/community/015124597bf67ba8012193a32d741b.jpg@2o.jpg">
        </p>
      </figure>
      <div class="media-content">
        <div class="content">
          <p>
            <small>昵称</small>
            <strong> {{name}}</strong>
            <br>
          </p>
          <p>
            <small>创建于</small>
            <strong>{{updateTime}}</strong>
          </p>
        </div>


        <nav class="level is-mobile">
          <div class="level-left">
            <a class="level-item">
              <span class="icon is-small"><i class="fas fa-reply"></i></span>
            </a>
            <a class="level-item">
              <span class="icon is-small"><i class="fas fa-retweet"></i></span>
            </a>
            <a class="level-item">
              <span class="icon is-small"><i class="fas fa-heart"></i></span>
            </a>
          </div>
        </nav>
      </div>
      <div class="media-right">
      </div>
    </article>
    <div class="level" style="margin-top: 40px">
      <div class="level-item has-text-centered">
        <div>
          <p class="heading">账号</p>
          <p class="title">{{username}}</p>
        </div>
      </div>
      <div class="level-item has-text-centered">
        <div>
          <p class="heading">密码</p>
          <p class="title">{{password}}</p>
        </div>
      </div>
      <div class="level-item has-text-centered">
        <div>
          <p class="heading">年级</p>
          <p class="title">{{book}}</p>
        </div>
      </div>
      <div class="level-item has-text-centered">
        <div>
          <p class="heading">创建的时间</p>
          <p class="title">{{createTime}}</p>
        </div>
      </div>
      <div class="level-item has-text-centered">
        <div>
          <p class="heading">更新的时间</p>
          <p class="title">{{updateTime}}</p>
        </div>
      </div>
    </div>
    <br>
    <nav class="level">
      <div class="level-item has-text-centered">
        <div>
          <p class="heading">书体</p>
          <p class="title">3,456</p>
        </div>
      </div>
      <div class="level-item has-text-centered">
        <div>
          <p class="heading">Following</p>
          <p class="title">123</p>
        </div>
      </div>
      <div class="level-item has-text-centered">
        <div>
          <p class="heading">Followers</p>
          <p class="title">456K</p>
        </div>
      </div>
      <div class="level-item has-text-centered">
        <div>
          <p class="heading">Likes</p>
          <p class="title">789</p>
        </div>
      </div>
    </nav>

    <nav class="level">
      <div class="level-item has-text-centered">


      </div>

      <div class="level-item has-text-centered">


      </div>
      <div class="level-item has-text-centered">

        <div>

        </div>
      </div>
    </nav>

    <div class="card">
      <header class="card-header">
        <p class="card-header-title">
          <strong>刷题</strong><span class="tag is-dark">{{answerStatus}}</span>
        </p>
      </header>
      <div class="card-content">
        <div class="columns">
          <div class="column is-2">
            <p class="title">进度</p>
          </div>
          <div class="column is-8">
            <progress style="margin-top:10px;margin-left: 10px; margin-right: 10px" class="progress is-primary"
                      value="50" max="100">50%
            </progress>
          </div>
          <div class="column is-2">
            <p class="title">{{answerPercent}}%已完成</p>
          </div>
        </div>

        <div class="columns">
          <div class="column is-2">
            <p style="margin-top: 12px" class="title">操作</p>
          </div>

          <div class="column">
            <a id="start20" class="button is-warning is-large">开始20%</a>
            <a id="start50" class="button is-warning is-large">开始50%</a>
            <a id="start100" class="button is-warning is-large">开始100%</a>
            <a id="startLeft" class="button is-warning is-large">开始剩下全部</a>
          </div>

        </div>


      </div>


    </div>

    <div class="card" style="height: 300px; overflow: scroll">
      <header class="card-header">
        <p class="card-header-title">日志</p>
      </header>
      <table class="table is-bordered is-striped is-narrow is-hoverable is-fullwidth">
        <thead>
        <tr>
          <th><abbr title="发生的时间">时间</abbr></th>
          <th><abbr title="日志内容">内容</abbr></th>
          <th><abbr title="当时的百分比">进度</abbr></th>
        </tr>
        </thead>

        <tbody>
        <tr>
          <th>2016-9-10</th>
          <td>第24页完成 分数89</td>
          <td>38%</td>
        </tr>
        <tr>
          <th>2016-9-10</th>
          <td>第24页完成 分数89</td>
          <td>38%</td>
        </tr>
        <tr>
          <th>2016-9-10</th>
          <td>第24页完成 分数89</td>
          <td>38%</td>
        </tr>
        <tr>
          <th>2016-9-10</th>
          <td>第24页完成 分数89</td>
          <td>38%</td>
        </tr>
        <tr>
          <th>2016-9-10</th>
          <td>第24页完成 分数89</td>
          <td>38%</td>
        </tr>
        <tr>
          <th>2016-9-10</th>
          <td>第24页完成 分数89</td>
          <td>38%</td>
        </tr>
        <tr>
          <th>2016-9-10</th>
          <td>第24页完成 分数89</td>
          <td>38%</td>
        </tr>
        <tr>
          <th>2016-9-10</th>
          <td>第24页完成 分数89</td>
          <td>38%</td>
        </tr>
        <tr>
          <th>2016-9-10</th>
          <td>第24页完成 分数89</td>
          <td>38%</td>
        </tr>
        <tr>
          <th>2016-9-10</th>
          <td>第24页完成 分数89</td>
          <td>38%</td>
        </tr>
        <tr>
          <th>2016-9-10</th>
          <td>第24页完成 分数89</td>
          <td>38%</td>
        </tr>
        <tr>
          <th>2016-9-10</th>
          <td>第24页完成 分数89</td>
          <td>38%</td>
        </tr>
        <tr>
          <th>2016-9-10</th>
          <td>第24页完成 分数89</td>
          <td>38%</td>
        </tr>
        <tr>
          <th>2016-9-10</th>
          <td>第24页完成 分数89</td>
          <td>38%</td>
        </tr>
        <tr>
          <th>2016-9-10</th>
          <td>第24页完成 分数89</td>
          <td>38%</td>
        </tr>
        <tr>
          <th>2016-9-10</th>
          <td>第24页完成 分数89</td>
          <td>38%</td>
        </tr>
        <tr>
          <th>2016-9-10</th>
          <td>第24页完成 分数89</td>
          <td>38%</td>
        </tr>
        <tr>
          <th>2016-9-10</th>
          <td>第24页完成 分数89</td>
          <td>38%</td>
        </tr>
        <tr>
          <th>2016-9-10</th>
          <td>第24页完成 分数89</td>
          <td>38%</td>
        </tr>
        <tr>
          <th>2016-9-10</th>
          <td>第24页完成 分数89</td>
          <td>38%</td>
        </tr>
        <tr>
          <th>2016-9-10</th>
          <td>第24页完成 分数89</td>
          <td>38%</td>
        </tr>
        <tr>
          <th>2016-9-10</th>
          <td>第24页完成 分数89</td>
          <td>38%</td>
        </tr>
        <tr>
          <th>2016-9-10</th>
          <td>第24页完成 分数89</td>
          <td>38%</td>
        </tr>
        </tbody>
      </table>
    </div>

    <br>

  </div>

</template>

<script>
  export default {
    name: 'title',
    data() {
      return {
        name: 'shenjack',
        answerStatus: '空闲中',
        msg: 'Welcome to Your Vue.js App',
        username: '161002516',
        password: 'password',
        book: '大二下',
        createTime: '2016-08-08',
        updateTime: '2016-08-08',
        answerPercent: '50'
      }
    }
  }

</script>
