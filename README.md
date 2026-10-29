# 我的工具试用记录

这里保存工具链接、安装条件和实际试用结果。

## 记录什么

- 项目名称与链接：MediaCrawler  
  https://github.com/NanmiCoder/MediaCrawler
- 使用环境与版本（所有git python都最新版本）
  mac  2026/10/29
- 操作过程与结果：按照readme安装本地环境，clone project到本地安装成功之后，开启cmd运行命令：
  （creator_id博主id：
  https://www.xiaohongshu.com/user/profile/565fa0efcb35fb7876dbb07a?xsec_token=ABcGlRueG5JbDdirDv35BnnXJiYGY4hELhDJFXS2pFw6I%3D&xsec_source=pc_search
  profile/和下一个？之间
  这一份是爬取博主所有数据，一般crawler_max_notes_count 50即可
```bash
python main.py \
  --platform xhs \
  --lt qrcode \
  --type creator \
  --creator_id "565fa0efcb35fb7876dbb07a" \
  --get_comment true \
  --get_sub_comment true \
  --max_comments_count_singlenotes 50 \
  --crawler_max_notes_count 75 \
  --save_data_option csv
```
- 重开另外一个cmd里，清除所有chrome后台进程
```bashk
killall -9 "Google Chrome"
```
- base_config.py里面修改False至True
```bash
# 程序结束时是否自动关闭浏览器
# 设置为 False 可以保持浏览器运行，方便调试
AUTO_CLOSE_BROWSER = True
```


## 当前状态

- 运行结果：运行成功
- 本地操作：爬取小红书博主数据存储到当地project下的data目录中csv，有两个csv，一个是小红书博主发表的博文csv，包括博文数量为列数，博文内容爬取为内容，另外一个csv是爬取评论数据进行存储
- 运行结果：获取2份csv，后续做数据分析用
- 防坑指南：chrome一定要关干净、小红书最好用大陆ip登录（挂代理很慢）、小红书不要频繁爬（停10分钟或者一晚上，反爬虫引发风控），mac所有系统环境最好是最新的（小红书更新很快）、py命令启起来之后要手动扫码登录xhs、chrome上看不到爬取痕迹后台自动爬、一切以cmd上finish结束为准如果有error或者不打log，之间ctr+c、mac做好python版本管理

