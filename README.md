# Testlib for Lemons

Testlib for Lemons 添加了 Testlib 对本地自定义测试和 Lemon 系评测软件的 Special Judge 的支持。

对于本地自定义测试，可以使用 `registerLocalChecker(<Input_File>, <Output_File>, <Answer_File>, <Perfect_Score>, <Score_File>[, <Report_File>])` 的格式进行初始化，其中 `<Perfect_Score>` 表示该测试点的满分，`<Score_File>` 表示将该测试点得分输出到的文件的文件名，`<Report_File>` 表示附加信息的输出位置，可以不填（如果不填则不会输出附加信息）。

对于 Lemon 系评测软件的 Special Judge，可以直接使用 `registerLemonChecker(argc, argv)`，类似正常使用 Testlib 的 checker 功能时的操作。

### 新功能

相对于 matthew99 的版本，除了 Testlib 本身的更新，还添加了以下新功能：

- 还可以使用 `quitf(_pc(score), ...)` 返回测试点的部分分数了。注意 `score` 必须是整数。
- `quitp(score, ...)` 时测试点分数变为四舍五入。
- 提供了 `bool quitpRelativeScoring` 变量，默认为 `false`，  
  若设置为 `true` 则 `quitp(score, ...)` 时 `score` 的意义改为得分比例，返回的分数根据 `perfectScore` 按比例调整。
- 提供了 `bool partialScoreTrimming` 变量，默认为 `false`，  
  若设置为 `true` 则 `quitp(score, ...)` 时强制令最终得分不为 0 或 `perfectScore`，即一定获得部分分数。
- 添加了宏 `TESTLIB_FOR_LEMONS`。可以用来确保 checker 的跨平台兼容性。

-----

Testlib for Lemons 的宣传博客：[新版的 Testlib for Lemons 与对 Lemon 系列评测软件的介绍 - 粉兔 - 博客园](https://www.cnblogs.com/PinkRabbit/p/Testlib-for-Lemons.html)。

LemonLime 的仓库地址：[github.com/Project-LemonLime/Project_LemonLime](https://github.com/Project-LemonLime/Project_LemonLime)。

LemonLime 在用户手册中帮助宣传了 Testlib for Lemons，感谢他们！
