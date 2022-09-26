# 模块0：安装和配置 `node` 项目环境

以下默认操作系统为 Windows 。

## 下载和安装

JavaScript 语言是前端开发的基石，在后端开发中也有很多应用。在前端， JavaScript 代码内嵌或外联在 html 文件中，被**浏览器**识别并执行。浏览器之外， `Node.js` 提供了 JS 代码的第二套运行环境。

- `Node.js`
    
    - [下载](https://nodejs.org/en/download/current/)。一般是 Win 64位。安装很傻瓜，照做即可。注意勾选“添加至环境变量”。
    - 检查安装和配置是否成功：命令行执行 `node -v` ，将会输出你安装的版本号。

- `npm`

    - 即 node package manager，是 `node` 项目的包管理工具。实际开发中我们不可能经常自己造轮子，绝大多数时候是在寻找、学习使用和整合社区中的各种工具，即“包”、“库”。包从哪来？ `npm` 提供了这个平台和配套的下载配置工具。
    - 安装 `node` 时内置了一定版本的 `npm` 。命令行执行 `npm -v` 可以查看

- 在 `node` 中体验 Javascript
    命令行执行 `node` 将会激活 `node` 命令行环境。类似于 `python` 和 `R` 的命令行。执行 `.exit` 退出。

## 创建 React.js 项目

- 在本文件夹内，执行 `npx create-react-app first-app` ，这将在本文件夹内创建一个 `first-app` 文件夹，内部包含一个 react.js 模板项目。进入 `first-app` 文件夹，命令行执行 `npm start` ，将会运行这个模板应用，默认运行在本机的 `3000` 端口，可以在浏览器内通过 `http://localhost:3000/` 访问。
- 以上创建的默认项目里，可以开始 React 提供的 [`tik-tac-toe` 教程](https://reactjs.org/tutorial/tutorial.html)，或 Mozilla 提供的 [日程表教程](https://developer.mozilla.org/en-US/docs/Learn/Tools_and_testing/Client-side_JavaScript_frameworks#react_tutorials)。我们的项目将会更接近后者。
- 注意模板项目的结构 
    - `package.json`
      包含了项目的配置信息，包括名称、可执行脚本、证书、**依赖**等。依赖是这个项目直接使用的外部包。 `npm install` 命令将会安装本文件内声明的依赖。 `npm install <package identifier>` 将会在当前文件夹内安装指定的包并添加到 `package.json` 依赖，只能在当前文件夹内使用。添加 `-g` 选项将会把包安装到全局，在当前文件夹之外也可以使用。
    - `package-lock.json`
      项目的直接依赖一般还会依赖于其他包，形成复杂的依赖网络，手动逐一安装这些次级依赖是不可行的。好在 `npm` 会自动解析这些次级依赖并写入该文件。
    - `node_modules`
       外部包的安装目录。如果正在使用 `git` 等版本控制工具，请务必将该文件夹添加到忽略目录中(如 `.gitignore` 配置文件中)。
    - 其他目录是可自定义的。