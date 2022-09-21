# CodeBlender
A blender to blend your code into soup

Current declaration are only provided in Chinese. No English versions are provided.

In no case will we be reliable to the stability of meaning of declaration if it was translated into other languages.

定义：

- 本程序：指 CodeBlender 及其一切衍生程序产品，包括但不限于源代码、二进制文件、各类数据文件等；
- 开发者：指对 CodeBlender 的开发提供过实际支持，包括但不限于提供源代码、二进制文件、各类数据文件等的个体。

当您在使用本程序的时候，默认：
1. 您知晓且同意本程序并非用于商业用途的混淆。本程序不提供也无法提供具有商业级的反混淆难度的混淆功能。
2. 您知晓且同意本程序仅供学习交流使用。开发者不对因使用本程序造成的任何侵权等事件负责。
3. 您知晓且同意，开发者不对因在对代码著作权有要求（包括但不限于各 OJ）上使用本程序抄袭他人程序导致的封号等直接或间接的一切形式的损失承担责任。
4. 本代码遵循 GNU 3.0 开源协议。本声明目前没有英文版本。
5. 开发者保留一切解释权。


在某些时刻可能需要把一些小 cpp 代码混淆起来，CodeBlender 便是为此设计。

使用方式：

1. **将源代码下载并编译**。在开发者的设备上该代码可以正常编译运行。（相关参数：编译器 TDM-GCC 4.9.2 64bit-release，开启 `-std=c++11`。你并不必须完全按照该参数来）

2. CLI 启动方式：运行编译后生成的可执行文件，直接键入代码，使用 `Ctrl+Z` 终止输入，你将从屏幕中看到混淆后的结果。
3. 命令行启动方式：运行 `codeblender <input-file> <output-file> [{options}]`。

`options` 可以有任意多个，如：

- `codeblender a.cpp b.cpp`：将 a.cpp 混淆后输出至 b.cpp（使用默认设置————见下）；
- `codeblender a.cpp b.cpp -keepnum -space`：将 a.cpp 混淆后输出至 b.cpp，保留所有数字不进行混淆、随机插入空格 / 制表符；
- `codeblender a.cpp b.cpp -sortname`：将 a.cpp 混淆后输出至 b.cpp，并将所有识别到的标识符按字典序混淆。

| 选项 | 默认值 | 描述 |
| :-----------: | :-----------: | :-----------: |
| `--keepnum` | 1 | 开启后保留所有数字不进行混淆 |
| `--keepstr` | 1 | 开启后保留所有字符串不进行混淆  |
| `-keepvar` | 1 | 开启后保留所有识别到的标识符不进行混淆 |
| `--space` | 0 | 开启后随机插入空格 / 制表符 |
| `--comment` | 0 | 开启后随机插入无意义注释 |
| `--sortname` | 0 | 开启后将所有识别到的标识符按照 `a`、`b`...`z`、`aa`、`ab`... 的顺序混淆；关闭后使用随机字符串混淆 |


当前 issue：

- 过大的数字可能会导致掉精度。
- 可能会将 `operator` 等关键字当作标识符混淆。
- 若代码中存在与 STL 重名的标识符，可能会将 STL 的函数调用均混淆掉。
- 可能无法完全识别所有标识符。

开发者实测：对于有一定代码力的人，当混淆不超过 200 行的 OI 竞赛风格代码时，通过编译器的报错信息可以相当快地解决错误。
