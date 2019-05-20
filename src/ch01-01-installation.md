## Installation/安装

The first step is to install Rust. We’ll download Rust through `rustup`, a
command line tool for managing Rust versions and associated tools. You’ll need
an internet connection for the download.

第一步是安装Rust。 我们将通过`rustup`下载Rust，这是一个用于管理Rust版本和相关工具的命令行工具。 您需要一个互联网连接才能下载。


> Note: If you prefer not to use `rustup` for some reason, please see [the Rust
> installation page](https://www.rust-lang.org/tools/install) for other options.

>注意：如果您因某些原因不想使用`rustup`，请参阅[Rust
>安装页面]（https://www.rust-lang.org/tools/install）了解其他选项。

The following steps install the latest stable version of the Rust compiler.
Rust’s stability guarantees ensure that all the examples in the book that
compile will continue to compile with newer Rust versions. The output might
differ slightly between versions, because Rust often improves error messages
and warnings. In other words, any newer, stable version of Rust you install
using these steps should work as expected with the content of this book.

以下步骤安装Rust编译器的最新稳定版本。
Rust的稳定性保证了书中编译的所有示例都将继续使用较新的Rust版本进行编译。 版本之间的输出可能略有不同，因为Rust通常会改进错误消息和警告。 换句话说，使用这些步骤安装的任何较新的稳定版本的Rust应该按照本书的内容正常工作。


> ### Command Line Notation
>
> In this chapter and throughout the book, we’ll show some commands used in the
> terminal. Lines that you should enter in a terminal all start with `$`. You
> don’t need to type in the `$` character; it indicates the start of each
> command. Lines that don’t start with `$` typically show the output of the
> previous command. Additionally, PowerShell-specific examples will use `>`
> rather than `$`.

> ### 命令行表示法
>
>在本章和整本书中，我们将展示终端中使用的一些命令。 您应该在终端中输入的行都以`$`开头。 
>你不需要输入`$`字符; 它表示每个命令的开始。 不以`$`开头的行通常显示上一个命令的输出。 
>另外，PowerShell特定的示例将使用`>`而不是`$`。

### Installing `rustup` on Linux or macOS/在Linux或macOS上安装`rustup`

If you’re using Linux or macOS, open a terminal and enter the following command:

```text
$ curl https://sh.rustup.rs -sSf | sh
```
如果您使用的是Linux或macOS，请打开终端并输入以下命令：

```text
$ curl https://sh.rustup.rs -sSf | sh
```

The command downloads a script and starts the installation of the `rustup`
tool, which installs the latest stable version of Rust. You might be prompted
for your password. If the install is successful, the following line will appear:

该命令下载脚本并开始安装`rustup`工具，该工具安装最新的稳定版Rust。 系统可能会提示您输入密码。 如果安装成功，将显示以下行：

```text
Rust is installed now. Great!
```

If you prefer, feel free to download the script and inspect it before running
it.
如果您愿意，可以随意下载脚本并在运行之前进行检查。

The installation script automatically adds Rust to your system PATH after your
next login. If you want to start using Rust right away instead of restarting
your terminal, run the following command in your shell to add Rust to your
system PATH manually:

下次登录后，安装脚本会自动将Rust添加到系统PATH中。 如果您想立即开始使用Rust而不是重新启动终端，请在shell中运行以下命令以手动将Rust添加到系统PATH：


```text
$ source $HOME/.cargo/env
```

Alternatively, you can add the following line to your *~/.bash_profile*:

或者，您可以将以下行添加到*〜/ .bash_profile *：

```text
$ export PATH="$HOME/.cargo/bin:$PATH"
```

Additionally, you’ll need a linker of some kind. It’s likely one is already
installed, but when you try to compile a Rust program and get errors indicating
that a linker could not execute, that means a linker isn’t installed on your
system and you’ll need to install one manually. C compilers usually come with
the correct linker. Check your platform’s documentation for how to install a C
compiler. Also, some common Rust packages depend on C code and will need a C
compiler. Therefore, it might be worth installing one now.

此外，您还需要某种链接器。 默认情况下可能已经安装了一个，但是当您尝试编译Rust程序并获得指示链接器无法执行的错误时，这意味着系统上未安装链接器，您需要手动安装链接器。 C编译器通常带有正确的链接器。 查看平台的文档，了解如何安装C编译器。 另外，一些常见的Rust包依赖于C代码，需要一个C编译器。 因此，为了以防万一，可能值得安装一个。

### Installing `rustup` on Windows

On Windows, go to [https://www.rust-lang.org/tools/install][install] and follow
the instructions for installing Rust. At some point in the installation, you’ll
receive a message explaining that you’ll also need the C++ build tools for
Visual Studio 2013 or later. The easiest way to acquire the build tools is to
install [Build Tools for Visual Studio 2019][visualstudio]. The tools are in
the Other Tools and Frameworks section.

在Windows上，转到[https://www.rust-lang.org/tools/install][install]并按照安装Rust的说明进行操作。 在安装的某个时刻，您将收到一条消息，说明您还需要Visual Studio 2013或更高版本的C ++构建工具。 获取构建工具的最简单方法是安装[Visual Studio 2019的构建工具] [visualstudio]。 这些工具位于“其他工具和框架”部分。

[install]: https://www.rust-lang.org/tools/install
[visualstudio]: https://www.visualstudio.com/downloads/#build-tools-for-visual-studio-2019


The rest of this book uses commands that work in both *cmd.exe* and PowerShell.
If there are specific differences, we’ll explain which to use.

本书的其余部分使用可在* cmd.exe *和PowerShell中使用的命令。 如果存在具体差异，我们将解释使用哪种差异。

### Updating and Uninstalling 更新和卸载

After you’ve installed Rust via `rustup`, updating to the latest version is
easy. From your shell, run the following update script:

通过`rustup`安装Rust后，更新到最新版本很容易。 在shell中，运行以下更新脚本：

```text
$ rustup update
```

To uninstall Rust and `rustup`, run the following uninstall script from your
shell:

要卸载Rust和`rustup`，请从shell运行以下卸载脚本：

```text
$ rustup self uninstall
```

### Troubleshooting 故障排除

To check whether you have Rust installed correctly, open a shell and enter this
line:

要检查是否正确安装了Rust，请打开shell并输入以下行：


```text
$ rustc --version
```

You should see the version number, commit hash, and commit date for the latest
stable version that has been released in the following format:

您应该看到以下列格式发布的最新稳定版本的版本号，提交哈希值和提交日期：

```text
rustc x.y.z (abcabcabc yyyy-mm-dd)
```

If you see this information, you have installed Rust successfully! If you don’t
see this information and you’re on Windows, check that Rust is in your `%PATH%`
system variable. If that’s all correct and Rust still isn’t working, there are
a number of places you can get help. The easiest is the #beginners channel on
[the official Rust Discord][discord]. There, you can chat with other Rustaceans
(a silly nickname we call ourselves) who can help you out. Other great
resources include [the Users forum][users] and [Stack Overflow][stackoverflow].

如果您看到此信息，则表示您已成功安装Rust！ 如果您没有看到此信息并且您在Windows上，请检查Rust是否在您的`％PATH％`系统变量中。 如果这一切都正确并且Rust仍然无法正常工作，那么有很多地方可以获得帮助。 最简单的是[官方Rust Discord] [discord]上的#beginners频道。 在那里，你可以和其他Rustaceans（我们称之为傻傻的昵称）聊天，他们可以帮助你。 其他优秀的资源包括[用户论坛] [用户]和[Stack Overflow] [stackoverflow]。

[discord]: https://discord.gg/rust-lang
[users]: https://users.rust-lang.org/
[stackoverflow]: http://stackoverflow.com/questions/tagged/rust

### Local Documentation

The installer also includes a copy of the documentation locally, so you can
read it offline. Run `rustup doc` to open the local documentation in your
browser.


安装程序还在本地包含文档的副本，因此您可以脱机阅读。 运行`rustup doc`以在浏览器中打开本地文档。

Any time a type or function is provided by the standard library and you’re not
sure what it does or how to use it, use the application programming interface
(API) documentation to find out!

只要标准库提供了类型或函数，并且您不确定它的作用或使用方法，请使用应用程序编程接口（API）文档来查找其用法和示例。