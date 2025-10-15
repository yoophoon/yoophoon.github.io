# 目录
```Text
.
├── __.config               博客配置文件
├── __.scaffolds            front-matter模板文件
├── _data                   一些页面的数据文件
├── _drafts                 草稿文件
├── _posts                  文章
├── asset                   资源文件夹
├── categories              分类|框架需要
├── link                    连接
├── movies                  电影列表
└── tags                    标签|框架需要
```
# 创建博客工作流
> 为了防止自己忘记怎么怎么创建博客

1. hexo init projectname
2. pnpm add hexo-theme-butterfly
3. 使用仓库文件替换博客项目source文件夹下的所有文件
4. 复制hexo-theme-butterfly模块内的config.yaml至博客项目的根目录并重命名为_config.butterfly.yaml
5. 使用VSCode的compare命令对比__.config文件夹内的文件与博客根目录的配置文件