
- 实时状态监控：服务器运行状态显示
- 日志窗口：实时查看操作日志
- 一键控制：启动/停止服务器、打开网站

## 🌐 Web文件服务器
- 基于HTTP协议的Web文件管理服务
- 支持局域网多设备访问
- 自动获取本机IP地址显示访问链接
- 可自定义端口号(默认65516)
- 支持优雅停止（捕获 Ctrl+C 等终止信号）


## 📁 核心文件管理功能
- 文件浏览：目录树形结构展示
- 文件上传：支持多文件上传和断点续传
- 文件下载：支持大文件下载和范围请求

### 文件操作：
- 目录浏览：展示文件和文件夹列表，支持导航到上级目录
- 文件操作：创建 / 删除文件、创建 / 删除文件夹 复制、移动、重命名
- 文件传输：上传文件（支持断点续传）、下载文件（支持断点续传）
- 批量操作：批量移动、批量删除
- 文件操作权限控制：限制操作范围在指定工作目录内
- 文件搜索：支持当前目录和全局搜索

### 📁 文件预览与播放支持
图片预览：支持 JPEG、PNG、GIF、WebP 等格式
- 缩放、旋转、拖拽查看
- 全屏模式
音频播放：支持 MP3、WAV、OGG、FLAC 等格式
- 连续播放功能
- 播放列表管理
- 快捷键控制
视频播放：支持 MP4、WebM、MOV、AVI 等格式
- 全屏播放
- 进度控制
- 格式兼容性检测
文档预览：支持 PDF 在线预览
文本文件预览：支持代码高亮显示

## 🔒 安全特性
- 删除保护：需要输入预设密码才能删除文件 （预置三组密码：Mysoy007、Mysoy9527、Mysoy1001）
- 路径安全：防止目录遍历攻击
- 权限控制：限制访问工作目录外的文件
- 文件名过滤：移除可能导致安全问题的特殊字符
- 详细的操作日志记录，便于问题排查和操作审计
- 日志格式包含时间、级别和消息内容，保存到 file_manager.log

## 🗃️ 数据库索引系统
- SQLite数据库存储文件索引
- 连接池管理提高并发性能
- 快速文件搜索和检索
- 自动目录扫描和索引更新
- 搜索范围：当前目录或全局搜索
- 搜索结果高亮：关键词高亮显示

## 📊 高级功能
- 断点续传：大文件上传支持断点续传
- 批量操作：支持多选文件的批量移动、删除
- 实时进度：上传下载进度显示
- 用户交互：操作结果提示信息
- 日志系统：详细的运行日志记录
- 支持文件大小的人性化显示（KB/MB）

### 🚀 性能优化
- 多线程服务器：支持并发请求处理
- 断点续传：大文件上传支持
- 缓存机制：图片、音视频流缓存
- 连接池：数据库连接复用

### 📊 日志系统
- 多级日志：DEBUG、INFO、WARNING、ERROR
- 双重输出：同时记录到文件和控制台
- GUI显示：实时在界面显示操作日志

## 🎯 用户体验优化
- 中文支持：完整的UTF-8编码支持
- 响应式设计：适配不同屏幕尺寸
- 操作确认：危险操作二次确认
- 状态反馈：实时操作结果提示

## 🔧 管理工具
- 日志查看：内置日志文件查看器
- 数据库状态检查：监控数据库健康状态
- 配置持久化：工作目录和设置记忆
- 一键访问：快速打开Web界面

## 🛠️ 技术特点
- 多线程服务器架构
- 异常处理和连接恢复
- 跨平台兼容(Windows/Linux/macOS)
- 断点续传：通过分割文件为块、记录已上传字节数实现断点续传功能
- 多线程处理：使用多线程服务器，支持同时处理多个客户端请求
- UTF-8 编码支持：全面支持中文文件名和路径
- 跨平台兼容：处理了 Windows 和类 Unix 系统的路径差异
- 临时文件管理：使用.upload_cache 目录存储上传中的临时文件

### 技术架构
- 后端：Python + http.server + SQLite
- 前端：HTML5 + CSS3 + JavaScript
- GUI：Tkinter
- 数据库：SQLite with connection pooling
- 线程模型：ThreadingTCPServer + 多线程处理

## 使用方法
### windows环境
- 解压后直接运行程序，默认使用程序当前目录作为工作目录
- 通过浏览器访问提示的地址（本地访问http://127.0.0.1:65516）
- 使用提供的删除密码进行删除操作

### linux环境
解压
tar -zxvf webfilemanager-linux-amd64-v4.3.tar.gz
直接运行
./webfilemanager-linux-amd64-v4.3
指定所有参数
./webfilemanager-linux-amd64-v4.3  --working-dir /path/to/files --log-dir /path/to/files --port 65516 --delete-passwords pwd1 pwd2 pwd3 

语法：
usage: tem_linux.py [-h] [--working-dir WORKING_DIR] [--log-dir LOG_DIR] [--port PORT]
                    [--delete-passwords DELETE_PASSWORDS DELETE_PASSWORDS DELETE_PASSWORDS] [--open-browser]

参数：
  -h, --help                                                                      查看帮助
  --working-dir, -d WORKING_DIR                                                   工作目录 (默认当前目录)
  --log-dir, -l LOG_DIR                                                           日志目录 (默认当前目录)
  --port, -p PORT                                                                 端口号 (默认: 65516)
  --delete-passwords, -w DELETE_PASSWORDS DELETE_PASSWORDS DELETE_PASSWORDS       删除密码，三个用空格分隔 (默认: Mysoy007 Mysoy9527 Mysoy1001)

示例：指定工作目录为/home 日志目录/home 端口为8086 删除密码为 001 002 003
./webfilemanager-linux-amd64-v4.3  --working-dir /home --log-dir /home --port 8086 --delete-passwords 001 002 003
