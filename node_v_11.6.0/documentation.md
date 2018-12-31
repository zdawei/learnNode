# About this Documentation 关于文档

The goal of this documentation is to comprehensively explain the Node.js API, both from a reference as well as a conceptual point of view. Each section describes a built-in module or high-level concept.

本文档的目的是从参考和概念来全面解释Node.js的API。每个章节描述了内部模块或者高级概念。

Where appropriate, property types, method arguments, and the arguments provided to event handlers are detailed in a list underneath the topic heading.

在适当的情况下，属性类型，方法参数，和提供给事件处理程序的参数将被详细列在主题标题下方的列表里。

# Contributing 贡献

If errors are found in this documentation, please submit an issue or see the contributing guide for directions on how to submit a patch.

如果发现错误，请提交issue或者查看贡献指南进行提交一个补丁。

Every file is generated based on the corresponding .md file in the doc/api/ folder in Node.js's source tree. The documentation is generated using the tools/doc/generate.js program. An HTML template is located at doc/template.html.

每个文件基于node.js源码树种的doc/api文件夹里的相关.mc文件生成的。本文档是使用tools/doc/generate.js程序生成。HTML模板在doc/template.html中。

# Stability Index 稳定性索引

Throughout the documentation are indications of a section's stability. The Node.js API is still somewhat changing, and as it matures, certain parts are more reliable than others. Some are so proven, and so relied upon, that they are unlikely to ever change at all. Others are brand new and experimental, or known to be hazardous and in the process of being redesigned.

在整个文档中都有关于部分稳定性的指示。 Node.js API仍在不断变化，随着它的成熟，某些部分比其他部分更可靠。有些是被证实，或者依赖，它们根本不可能改变。其他是全新的和实验性的，或者已知具有危险性并且在重新设计中。

The stability indices are as follows:

稳定性有如下几点：

Stability: 0 - Deprecated. The feature may emit warnings. Backward compatibility is not guaranteed.

Stability: 0 - 不推荐使用。该功能可能会发出警告。并且不保证向后兼容

Stability: 1 - Experimental. This feature is still under active development and subject to non-backward compatible changes or removal in any future version. Use of the feature is not recommended in production environments. Experimental features are not subject to the Node.js Semantic Versioning model.

Stability: 1 - 实验性质。这个功能仍在积极开发中，并且会在未来的版本中会受到非向后兼容的更改和删除。不建议在生产环境中使用该功能。实验性功能不会受到Node.js语义版本控制模型的约束。

Stability: 2 - Stable. Compatibility with the npm ecosystem is a high priority.

Stability: 2 - 稳定。兼容npm生态系统，是高优先级优先使用的部分。

Caution must be used when making use of Experimental features, particularly within modules that may be used as dependencies (or dependencies of dependencies) within a Node.js application. End users may not be aware that experimental features are being used, and therefore may experience unexpected failures or behavior changes when API modifications occur. To help avoid such surprises, Experimental features may require a command-line flag to explicitly enable them, or may cause a process warning to be emitted. By default, such warnings are printed to stderr and may be handled by attaching a listener to the 'warning' event.

在使用实验功能时必须谨慎，特别是在可能用作Node.js应用程序中的依赖项（或依赖项的依赖项）的模块中。最终用户可能不知道正在使用实验性功能，因此在API修改发生时可能会遇到意外故障或行为更改。为了避免此类意外，实验性功能可能需要命令行标志才能显式启用它们，或者可能导致发出进程警告。默认情况下，此类警告会打印到stderr，并且可以通过将侦听器附加到“warning”事件来处理。

# JSON Output 输出JSON

Stability: 1 - Experimental

Every .html document has a corresponding .json document presenting the same information in a structured manner. This feature is experimental, and added for the benefit of IDEs and other utilities that wish to do programmatic things with the documentation.

每个.html文档都有一个相应的.json文档，以结构化的方式呈现相同的信息。此功能是实验性的，并且为了IDE和其他工具希望使用文档执行编程工作的实用程序的好处而添加。

# Syscalls and man pages 系统调用和帮助手册

System calls like open(2) and read(2) define the interface between user programs and the underlying operating system. Node.js functions which simply wrap a syscall, like fs.open(), will document that. The docs link to the corresponding man pages (short for manual pages) which describe how the syscalls work.

像open（2）和read（2）这样的系统调用定义了用户程序和底层操作系统之间的接口。简单地包装系统调用的Node.js函数，如fs.open（），将记录它。文档链接到相应的手册页（手册页的简称），描述了系统调用的工作方式。

Most Unix syscalls have Windows equivalents, but behavior may differ on Windows relative to Linux and macOS. For an example of the subtle ways in which it's sometimes impossible to replace Unix syscall semantics on Windows, see Node.js issue 4760.

大部分Unix系统调用都在Windows上有对应的调用，但是行为可能和Linux和macOs稍有不同。有关在Windows上有时无法替换Unix系统调用语义的微妙方法的示例，请参阅Node.js issue 4760。
