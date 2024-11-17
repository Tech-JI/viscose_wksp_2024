## 配置C/C++ 编译器

### windows

- 下载MinGW [MinGW](https://sourceforge.net/projects/mingw-w64/)
- 解压安装包并安装
- 打开终端输入
    ```bash 
    gcc --version
    g++ --version
    gdb --version
    ```
    若出现了版本提示，则安装成功，否则需要手动配置环境变量

### Linux

- 打开终，输入 
    ```bash 
    gcc --version
    g++ --version
    gdb --version
    ```
    若出现了版本提示，可跳过安装编译器部分
- 未出现版本信息，则运行
    ```bash
    sudo apt install g++
    sudo apt install gcc
    sudo apt install gdb
    ```
- 出现安装请求提示时，键入 y 并按回车，完成安装

## VSCode C/C++ 插件

### 安装插件

- 打开扩展-应用商店 ![应用商店](assets/CExtension.png)
- 搜索C++，安装图示插件 ![C/C++扩展](assets/CExtension2.png)

### 配置插件

- 点击右侧齿轮按钮，选择设置![设置](assets/Settings.png)
- 搜索 compiler， 找到Compiler Path, 选择 在设置中编辑![Path](assets/compiler.png)
- 在终端中输入
    ```bash
    where.exe g++
    ```
    (windows)
    ```bash
    whereis g++
    ```
    (linux/mac)
- 将找到的g++路径写入settings.json的 **"C_Cpp.default.compilerPath": ""** (windows需要在每个反斜杠处多加一个反斜杠，示例： **"C_Cpp.default.compilerPath": "D:\\Program\\mingw64\\bin\\g++.exe",**)
