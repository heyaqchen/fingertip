# fingertip · 第二版使用说明

## 启动

需要 Python 3.10+。解压后双击 start.cmd，或运行 `python server.py`，打开 http://127.0.0.1:4182 。端口占用时用 `python server.py --port 4183`。

图片/PDF 识谱需先运行一次 `python setup_omr.py`，从官方 GitHub 下载 Audiveris 5.11.0 Windows x64 引擎，解压到 runtime，不安装系统服务。首次识别会写入用户 Audiveris 配置目录。当前开发电脑已准备好引擎。

## 功能

- 88 键 A0–C8 发声与五线谱定位；低、中、高音区分割线和色带。
- 练习 / 创作胶囊切换；12 类和弦、16 种常用符号。
- 两个知识窗口右上角进入记忆练习，12 种题型，每轮 10 题，首答计分。
- 自由弹逐音记录；复制到记录弹后添加和弦、休止、延音与同音连音，修改音高/时值、撤销、试听、导出 MusicXML / MIDI。
- 两份创作草稿分别本机自动保存，每份最多 512 项。刷新后撤销历史不保留，请导出重要作品备份。
- MusicXML / MXL / MIDI 导入，按声部/音轨、小节拆解，逐音试听校正，送入跟练或创作。
- PNG / JPEG / TIFF / BMP / PDF 本机识谱，原谱对照、校正、手动补入；最大 30 MB。

## 当前范围

- 自由弹每音默认一拍，节奏在记录弹编辑；未测量按键时长。声音为 Web Audio 合成音。
- 跟练检查音高顺序，和弦可依次弹出；未包含节奏评分、麦克风识别、外接 MIDI 键盘。
- 图片识谱适合清晰印刷谱，结果需要对照校正，复杂谱面可能耗时数分钟。文件存于本机 runtime/jobs，不上传云端。
- 学习谱面为简化排版，复杂时值用近似符形，实际拍数见拆解表。装饰音略过、反复段不自动展开，力度与踏板未完整还原。MusicXML 支持 score-partwise。
- 记录弹为顺序事件编辑器；复调请先选单声部，重叠 MIDI 送入编辑器会按事件顺序整理。创作导出统一 4/4，自动分小节并生成跨小节连音。
- 单文件 fingertip.html 可用核心功能与结构化曲谱导入；图片/PDF 自动识谱需要本地服务器。

## GitHub 复用与许可

已检索官方项目后引入以下库。版本和来源见 dist/vendor/manifest.json，MIT 许可证保存在同目录。

- [VexFlow 4.2.5](https://github.com/0xfe/vexflow)，MIT，五线谱绘制。
- [Tonejs/Midi 2.0.28](https://github.com/Tonejs/Midi)，MIT，MIDI 读写。
- [Tonal 6.5.1](https://github.com/tonaljs/tonal)，MIT，和弦计算。
- [fflate 0.8.2](https://github.com/101arrowz/fflate)，MIT，MXL 解压。
- [Audiveris 5.11.0](https://github.com/Audiveris/audiveris/tree/5.11.0)，AGPL-3.0，独立进程识谱。源码和许可证由该仓库提供。本源码包不附带引擎二进制，安装脚本从官方发布页下载；重新分发引擎或提供联网识谱服务需遵守该许可证。

此版本已在本机运行，尚未发布公网。
