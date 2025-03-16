# llmupdate.com
LLMUpdate, 大模型周报 -- 每周大模型和AI的重要进展，跟进值得关注的技术进步、产品创新

此仓库为 https://llupdate.com 大模型周报网站的内容镜像。

大模型周报上的内容如果有不正确的地方，您可以提交 Pull requests 到我们。


## Setup a Hugo github site

Hugo 创建静态网站 & 发布到 Github
https://themes.gohugo.io/themes/hugo-theme-jane/
https://gohugo.io/hosting-and-deployment/hosting-on-github/
https://github.com/xianmin/hugo-theme-jane/blob/master/README-zh.md


``` bash
hugo new site llmupdate
cd llmupdate
git clone https://github.com/adityatelange/hugo-PaperMod themes/PaperMod --depth=1
cd themes/PaperMod
git pull

#Copy the example site content:
cd ../../

# 配置文件：0.110.0 之后，配置文件改成了 hugo.toml。会依次找 hugo.toml, hugo.yaml, or hugo.json, config.toml 文件。

# hugo.toml 文件中指定 theme
vim hugo.toml
```

theme =  'PaperMod'

``` bash
# 配置 config.yml 文件
vim config.yml
```

内容参考：
https://github.com/adityatelange/hugo-PaperMod/wiki/Installation#sample-pagemd

``` bash
#Take a look at the example site:
hugo server

# The default content files are located in the ./content/post directory.
# Generate Site content as your website to the public/ directory:
hugo


Build static pages:
hugo -D

# Create new pages:  hugo new <SECTIONNAME>/<FILENAME>.<FORMAT>
cd llmupdate
hugo new post/my-first-post.md
```

##  使用 archytypes/post.md 的模板来创建页面
hugo new --kind post post/hello.md
hugo new --kind post post/manus-technique-report-20250315.md

llmupdate.com 上的文章内容采用 CC BY-NC 4.0 协议，可以在非商业场景下使用这些文章的全部/部分内容，需要注明出处。


