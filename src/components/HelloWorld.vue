<template>
  <div class="hello">
    <h1>{{msg}}</h1>
    <div class="container" style="width: 500px">
      <form action="${pageContext.request.contextPath}/LoginServlet" method="post">
        <div class="form-group">
          <label for="username" >用户名</label>
          <input type="text" name="username" class="form-control" id="username" placeholder="请输入账号"/>
        </div>
        <div class="form-group">
          <label for="password" >密码</label>
          <input type="password" name="password" class="form-control" id="password" placeholder="请输入密码"/>
        </div>
        <div class="form-inline">
          <label for="vcode">验证码：</label>
          <input type="text" name="verifycode" class="form-control" id="verifycode" placeholder="请输入验证码" style="width: 120px;"/>
          <a><img src="${pageContext.request.contextPath}/CheckCodeServlet" title="看不清点击刷新" id="img"/></a>
        </div>
        <hr/>
        <div class="form-group" style="text-align: center;">
          <input class="btn btn btn-primary" type="submit" value="登录">
        </div>
      </form>
      <c:if test="${error!=null}">
        <div class="alert alert-warning alert-dismissible" role="alert">
          <button type="button" class="close" data-dismiss="alert" >
            <span>&times;</span>
          </button>
          <strong>${error}</strong>
        </div>
      </c:if>
    </div>
  </div>
</template>

<script>
  import 'bootstrap/dist/css/bootstrap.min.css'
  import 'jquery/dist/jquery.min.js'
  import 'bootstrap/dist/js/bootstrap.js'
export default {
  name: 'HelloWorld',
  props: {
    msg: String
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
