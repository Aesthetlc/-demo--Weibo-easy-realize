# Weibo easy realize
实现新浪微博的增删（利用localStorage存储到浏览器中，实现刷新不清空的效果）

## 思路：

- DOM节点操作：**在点击删除的时候，把对应li从ul里面移除**；
- 本地化数据更新：**删除对应的那条数据及整个列表数组，那我怎么知道我要删除哪个？**
  - 唯一的ID：
    - ID：identification身份证，保证该数据绝对的唯一，我们就能找到它；
    - 构成：采用 时间戳+随机数，基本可以保证不会重复；
  - 生成ID，在发布阶段生成：
    - 新增DOM节点，修改DOM节点内容同时，把新增的ID通过赋值为自定义属性的方式加进去；
    - 本地数据，把ID存进去；
  - 删除：有了发布时新增的ID，点击删除时，获取点击对象的自定义属性ID，
    - DOM去除：删除DOM，
    - 数据去除：根据唯一的ID去找当前的数组内的数据，剔除掉；完成更新本地数据；
   
## 案例效果：

![Image text](https://raw.githubusercontent.com/Aesthetlc/img-folder/master/Weibo-easy-realize.gif)
