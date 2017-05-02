hexo 在写作的时候，如果在文中添加`<!--more-->`则该标记之前的部分就会成为该文章的简述，显示在首页里。但自己一直感觉如果可以自行截取会更好，Google 了一下也有人有这样的需求，太没有贴出来具体的方法，在简单的学习了一下 JS 之后贴出自己的解决方案。
在 hexo 的 github 上看到有人说是跟主题有关，费死八难找到了代码的关键部分：文件`/themes/[主题名]/layout/_partial/article.ejs`其中有一段为：

```javascript
<div class="article-entry" itemprop="articleBody">
  <% if (post.excerpt && index) { %>
    <%- post.excerpt %>
    <% if (theme.excerpt_link) { %>
      <p class="article-more-link">
        <a href="<%- config.root %><%- post.path %>#more"><%= theme.excerpt_link %></a>
      </p>
    <% } %>
  <% } else { %>
  	  <%- post.content %>
  <% } %>
</div>
```

从代码上看，post.excerpt 就是加了 more 标记之后的文章摘要，如果 post.excerpt 存在且在首页的话，则显示文章的摘要和「Read More」按钮。当不符合上述条件（post.excerpt 存在且在首页），就显示整个文章的内容 post.content。

因为我需要的是在文章里没有 more 标记时自动添加标记，所以需要改动的代码是要放在 else 后面的。我打算在文章没有 more 标记的时候，截取文章的前两段作为摘要，如果文章少于两段，则直接显示整篇文章内容。

所以代码大概是这样：

```javascript
var count = 0
var content = post.content
while(count < 4) {
  content = content.replace('\n','x')
}
var br = content.indexOf('\n') // 第一个换行符所在的位置
if (br == -1 || !index) { // 如果不存在第一个换行符或者不在首页
  post.content // 显示整篇文章
} else {
  post.content.substring(0,br) // 截取到第二个换行符的位置
  // 显示「Read More」按钮
}
```

根据上述思路，修改后的代码为：

```javascript
<div class="article-entry" itemprop="articleBody">
  <% if (post.excerpt && index) { %>
    <%- post.excerpt %>
    <% if (theme.excerpt_link) { %>
      <p class="article-more-link">
        <a href="<%- config.root %><%- post.path %>#more"><%= theme.excerpt_link %></a>
      </p>
    <% } %>
  <% } else { %>
  	<% var br = post.content.indexOf('\n') %>
  	<% if(br < 0 || !index) { %>
  	  <%- post.content %>
  	<% } else { %>
  	  <%- post.content.substring(0, br) %>
  	  <% if (theme.excerpt_link) { %>
        <p class="article-more-link">
          <a href="<%- config.root %><%- post.path %>#more"><%= theme.excerpt_link %></a>
        </p>
      <% } %>
  	<% } %>
  <% } %>
</div>
```

如果需要截取 N 个段落，则可以使用 replace 替换 content 里 N-1 次`\n`然后使用 indexOf 即可。但是发现如果所要截取的部分有一半处于代码片段的话，就会很惨不忍睹。所以建议使用这种方法自动截取摘要的话，尽量为自己博客有代码的文章手动截取摘要。