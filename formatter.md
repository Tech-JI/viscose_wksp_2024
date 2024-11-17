# Formatter

## 介绍

- Formatter是由VSCode插件提供的自动格式化代码的功能。Formatter会自动调整代码的换行、符号左右的空格、缩进、单双引号、函数之间的间隔、调用库的顺序等，这样写代码的时候就不用在意这些，能让代码整洁美观。
- 代码有很多格式化的标准。VSCode默认的标准是`Visual Studio`。其他常用的标准有`Google`，`LLVM`，`Microsoft`，`GNU`等。

## 快捷键

在代码界面单击右键，可以看见选项`Fomat Document`，右侧显示了快捷键。Windows上快捷键是`Shift + Alt + F`，Linux上是`Ctrl + Shift + I`

## 默认格式化工具：

- 在代码界面单击右键，可以看见选项`Fomat Document With...`，点击即可选择格式化工具。单击`Configure Default Formatter...`可以选择该语言默认的格式化工具

- 也可以通过在设置中搜索`Format`或`格式化`的方式找到`Default Formatter`选项

- 可以通过编辑settings.json的方式手动设置formatter

  ```json
  "editor.formatOnSave": true,
      "[cpp]": {
          "editor.defaultFormatter": "ms-vscode.cpptools"
      },
  ```

## Misc

在设置中搜索`Format`或`格式化`，找到`Format On Paste`和`Format On Save`选项。前者在粘贴代码的时候会自动格式化。后者在保存的时候会自动格式化。如果未配置这两项，则需要手动通过快捷键格式化

## C/C++

- C和C++的格式化功能由C/C++插件提供

- 在settings.json中添加
    ```json
    "editor.formatOnSave": true,
        "[cpp]": {
            "editor.defaultFormatter": "ms-vscode.cpptools"
        },
    ```

- 如果想要调整format style，打开C/C++扩展，进入设置，在**C_Cpp: Clang_format_fallback Style**下进行设置[format](pic/cpp_format.png)
- 示例：
  ```json
  { BasedOnStyle: Google, UseTab: ForIndentation, IndentWidth: 4, TabWidth: 4, ColumnLimit: 100 }
  ```

## Python

- Python常用的格式化工具是black，可在插件市场安装。正式的Python项目中推荐使用black
- 还有个常用的格式化工具是yapf，可在插件市场安装。它对缩进、换行的支持更符合习惯

## Javascript/Typescript/Vue/React

- VSCode是使用Electron框架开发，界面由网页技术通过Chromium（浏览器内核）渲染。VSCode深度集成了前端技术，因此也内置了对所有前端语言的支持。VSCode默认的前端语言（html，css，javascript，typescript，vue，react等）的格式化工具是内置的
- 前端语言的常用格式化工具是prettier，可以从插件市场安装。推荐在前端项目中将prettier设置为默认的格式化工具

## Golang

VSCode的Go插件已经包含了格式化工具