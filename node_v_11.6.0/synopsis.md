# Usage 使用

`node [options] [V8 options] [script.js | -e "script" | - ] [arguments]`

Please see the Command Line Options document for information about different options and ways to run scripts with Node.js.

在Node.js下运行脚本，针对不同方法和操作的具体信息，请查看命令行操作文档

# Example 用例

An example of a web server written with Node.js which responds with 'Hello, World!':

一个使用Node.js响应'Hello, World!'的web服务器的例子：

Commands displayed in this document are shown starting with $ or > to replicate how they would appear in a user's terminal. Do not include the `$` and `>` characters. They are there to indicate the start of each command.

本文档中显示的命令以`$`或`>`开头，以复制它们在用户终端中的显示方式。不要包含`$`和`>`字符。它们用于指示每个命令行的开始。

There are many tutorials and examples that follow this convention: `$` or `>` for commands run as a regular user, and `#` for commands that should be executed as an administrator.

很多教程和用例都有如下的惯例，使用`$`和`>`作为普通用户执行的命令，使用`#`作为管理员所执行的命令。

Lines that don’t start with `$` or `>` character are typically showing the output of the previous command.

不是以`$`或者`>`开始的字符，其实是作为上一个命令的输出结果。

Firstly, make sure to have downloaded and installed Node.js. See this guide for further install information.

首先，确保下载并且安装了Node.js。为了获得更多的安装信息，请看这篇[指导](https://nodejs.org/en/download/package-manager/)

Now, create an empty project folder called projects, then navigate into it. The project folder can be named based on the user's current project title, but this example will use projects as the project folder.

现在，创建一个空项目文件夹，取名为projects，然后进入到此文件夹内。这个项目文件夹的名字可以基于用户当前项目标题，但是这个例子将会使用projetcs作为项目文件夹名。

Linux and Mac:

```
$ mkdir ~/projects
$ cd ~/projects
```
Windows CMD:
```
> mkdir %USERPROFILE%\projects
> cd %USERPROFILE%\projects
```
Windows PowerShell:
```
> mkdir $env:USERPROFILE\projects
> cd $env:USERPROFILE\projects
```

Next, create a new source file in the projects folder and call it hello-world.js.

下一步，在此项目内创建一个新文件，并取名为`hrllo-world.js`。

In Node.js it is considered good style to use hyphens (-) or underscores (_) to separate multiple words in filenames.

在Node.js里，为了考虑到最优风格，使用`-`和`_`来分割文件名。

Open hello-world.js in any preferred text editor and paste in the following content:

使用任意编辑器打开`hello-world.js`，并复制如下内容到文件内：

```javascript
const http = require('http');

const hostname = '127.0.0.1';
const port = 3000;

const server = http.createServer((req, res) => {
  res.statusCode = 200;
  res.setHeader('Content-Type', 'text/plain');
  res.end('Hello, World!\n');
});

server.listen(port, hostname, () => {
  console.log(`Server running at http://${hostname}:${port}/`);
});

```

Save the file, go back to the terminal window enter the following command:

保存文件，回到终端输入如下命令：

`$ node hello-world.js`

An output like this should appear in the terminal to indicate Node.js server is running:

终端应输出如下内容，已指明Node.js服务器已经运行：

`Server running at http://127.0.0.1:3000/`

Now, open any preferred web browser and visit http://127.0.0.1:3000.

现在，打开任意浏览器，并访问http://127.0.0.1:3000。

If the browser displays the string Hello, World!, that indicates the server is working.

如果浏览器显示Hello,World!， 则说明服务器已经开始工作。

Many of the examples in the documentation can be run similarly.

更多文档内的例子都是这样运行的。