网页

模板网页
---
layout: TEMPLATE
title: TITLE
---
CONTENT
TEMPLATE.html放在_layouts下面
TITLE在模板中用{{ page.title }}引用
CONTENT在模板中用{{ content }}引用

嵌套
{% include PAGE.html %} 
PAGE.html放在_includes下面

从数据渲染
{% for ITEM in site.data.CURRENT_TEMPLATE %}
CURRENT_TEMPLATE.yml放在_data下面
yml中的
- A: val
  B: val
用ITEM.A引用

博客
---
layout: TEMPLATE
variable: VALUE
---
CONTENT
放在_posts下面
TITLE用{{ post.title }}引用
{{ post.excerpt }}可以得到CONTENT的第一句话

自定义变量
上面模板博客中的variable放在_variable下面
