title: hexo
tags: []
categories: []
date: 2016-04-10 17:20:00
---

## 建站  
```
hexo init <folder>
cd <folder>
npm install
```
## 站点目录结构  
```
    |---node_modules    //node模块
    |---scaffolds       //文章模板
    |---source          //文章存放位置
    |---themes          //主题文件
    |---_config.yml     //站点配置文件
    |--package.json     //node配置文件
```

## 配置_config.yml  
###  网站  
 |参数            | 描述          |
 |:---------------|:--------------|
 |title           |网站标题       |
 |subtitle        |网站副标题     |
 |decription      |网站描述       |  
 |author          |作者名字       |
 |language        |语言           |
 |timezone        |网站时区       |   

###  网址  
 |参数            |描述             |
 |:---------------|:----------------|
 |url             |网址             |
 |root            |网站根目录       |
 |permalink       |文章永久链接格式 |
 |permlink_default|永久链接默认值   |

###  目录 
 |参数             |描述                |默认值         |
 |:----------------|:-------------------|:--------------|
 |public_dir       |公共文件夹          |public         |
 |tag_dir          |标签文件夹          |tags           |
 |archive_dir      |归档文件夹          |archives       |
 |catagory_dir     |分类文件夹          |categories     |
 |code_dir         |include code文件夹  |downloads/code |
 |i18n_dir         |国际化文件夹        |:lang          |
 |skip_render      |跳过渲染的文件夹    |               |

### 文章 
 |参数             |描述                         |默认值    |
 |:----------------|:----------------------------|:---------|
 |new_post_name    |新建文章的名称               |:title.md |
 |default_layout   |预设布局                     |post      |
 |auto_spacing     |中英文之间加空格             |false     |
 |titlecase        |                             |false     |
 |external_link    |在新标签中打开链接           |true      |
 |filename_case    |文件名称大小写(小写1，大写2) |0         |
 |render_drafts    |显示草稿                     |flase     |
 |post_asset_folder|启用Assets文件夹             |flase     |
 |relative_link    |链接相对位置                 |flase     |
 |future           |是否显示未来的文章           |ture      |
 |highlight        |代码块的位置                 | ---      |

### 分类和标签   
 |参数             |描述         |
 |:----------------|:------------|
 |defualt_category |默认分类名   |
 |category_map     |分类别名     |
 |tag_map          |标签别名     |

### 日期/时间格式 
 |参数             |描述     |默认值    |
 |:----------------|:--------|:---------|
 |data_format      |日期格式 |MMM D YYYY|  
 |time_format      |时间格式 |H:mm:ss   |

### 分页 
 |参数             |描述                           |默认值|
 |:----------------|:------------------------------|:-----| 
 |per_page         |每一页的文章数量(0表示关闭分页)|10    |
 |pagination_dir   |分页目录                       |page  | 

### 扩展
 |参数             |描述                     |
 |:----------------|:------------------------|
 |theme            |主题名称(false表示禁用)  |
 |deploy           |部署设置                 |

## 用法 
### init
```
hexo init [folder]
```
初始化站点目录  
### new 
```
hexo new [layout] <title>
```
新建一篇文章   
如果不指定layout参数,则使用站点配置的默认default_layout参数。如果标题中含有空格需要使用引号引起来。
###  generate 
```
hexo generate
```
生成静态文件  

 |选项             | 描述              |
 |:----------------|:------------------|
 |-d, --deploy     |生成并部署网站     |
 |-w, --watch      |监听文件变动       |

### publish
```
hexo publish [layout] <filename>
```
发表草稿
### server
```
hexo server
```
启动服务器 

 |选项                |描述            |
 |:-------------------|:---------------|
 |-p, --port          |指定端口        |
 |-s, --static        |只使用静态文件  |
 |-l, --log           |启动日志记录    | 

### deploy
```
hexo deploy
```
部署网站  
使用参数`-g, --generate`可以在部署前生成站点静态文件。  
### reander
```
hexo render <file> [file2] ...
```
渲染文件  
使用参数`-o, --output`设置输出路径。  
### migrate
```
hexo migrate <type>
```
从其他博客系统中迁移内容  
### clean
```
hexo clean
```
清除缓存文件(db.json)和已生成的静态文件  
### list
```
hexo list <type>
```
列出站点资料  
### version
```
hexo version
```
显示hexo版本  
### 选项
#### 安全模式 
```
hexo --safe
```
安全模式下不会载入脚本和插件。  
#### 调试模式
```
hexo --debug
```
调试模式下终端会显示调试信息并记录到debug.log文件中。  
#### 简洁模式 
```
hexo --silent
```
隐藏终端信息   
#### 自定义配置文件路径 
```
hexo --config custom.yml
```

#### 显示草稿   

```
hexo --draft
```

#### 自定义当前工作目录   

```
hexo -cwd /path/to/cwd
```

## 写作  
```
hexo new [layout] <title>
```
layout选项  

 |布局           |路径          |  
 |:--------------|:-------------|  
 |post           |source/_post  |  
 |page 			 |source        |  
 |draft			 |source/_draft |  
不需要处理时可以在Front-Matter中将layout设置为false。