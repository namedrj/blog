```html
<!DOCTYPE html>
<html lang="en">

<head>
  <meta charset="UTF-8">
  <title>demo01</title>
</head>

<body>
  <div id="box">
    <table border="1">
      <thead>
        <tr>
          <th>name</th>
          <th>age</th>
          <th>ins</th>
        </tr>
      </thead>
      <tbody id="bd">
        <!-- <tr>
          <td></td>
          <td></td>
          <td></td>
        </tr> -->
      </tbody>
    </table>

  </div>
  <!-- 
    模板引擎作用：数据与结构分离
    模板引擎使用步骤：
    1.构建模板
      <script type="text/html" id="temp">...</script>
    2.渲染数据
      <script>... var html = template("temp", data); ... innerHTML = html;</script>
   -->

  <!-- 简洁语法 -->
  <script type="text/html" id="temp">
    {{each data as value index}}
    <tr>
      <td>{{value.name}}</td>
      <td>{{value.age}}</td>
      <td>{{value.ins}}</td>
    </tr>
    {{/each}}
  </script>


  <!-- 原生语法 -->
  <script src="template-web.js"></script>
  <script>
    var data = [{
      name: 'skj',
      age: 18,
      ins: '打球'
    }, {
      name: 'zyt',
      age: 20,
      ins: '唱歌'
    }, {
      name: 'lp',
      age: 19,
      ins: '打游戏'
    }, {
      name: 'zz',
      age: 21,
      ins: '追剧'
    }];
    // 这里的 data 为 Object 类型，如果原数据是数组，需要包装成对象
    var html = template("temp", {
      "data": data
    });

    document.getElementById("bd").innerHTML = html;
  </script>
</body>

</html>
```
