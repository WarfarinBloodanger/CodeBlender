# CodeBlender
A blender to blend your code into soup

在某些时刻可能需要把一些小 cpp 代码混淆起来，CodeBlender 便是为此设计。

| 选项 | 默认值 | 描述 |
| :-----------: | :-----------: | :-----------: |
| `--keepnum` | 1 | 开启后保留所有数字不进行混淆 |
| `--keepstr` | 1 | 开启后保留所有字符串不进行混淆  |
| `-keepvar` | 1 | 开启后保留所有识别到的标识符不进行混淆 |
| `--space` | 0 | 开启后随机插入空格 / 制表符 |
| `--comment` | 0 | 开启后随机插入无意义注释 |
| `--sortname` | 0 | 开启后将所有识别到的标识符按照 `a`、`b`...`z`、`aa`、`ab`... 的顺序混淆；关闭后使用随机字符串混淆 |
