---
title: "F# 开发环境功能"
description: "了解在 F # 中支持的 Visual Studio 2012 的功能。"
keywords: "visual f#, f#, 函数编程"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 809e9a34-b271-4c87-8356-2426b44f4721
ms.openlocfilehash: 05727bf11eccfd64f823dd280b1a19210815ca5a
ms.sourcegitcommit: 685143b62385500f59bc36274b8adb191f573a16
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2017
---
# <a name="visual-f-development-environment-features"></a>Visual F# 开发环境功能

> [!NOTE]
本文不是最新的 Visual Studio 最新的。  它将会更新。

本主题包含有关哪些功能的 Visual Studio 2012 支持 F # 中的信息。

## <a name="project-features"></a>项目功能
下表总结了可用于在 F # 项目中使用的模板。 有关项目和项模板的信息，请参阅[NIB 从模板创建项目](https://msdn.microsoft.com/library/7c36d86a-6b79-4480-8228-0f925f1204b2)。

|模板类型|描述|支持的模板|
|-------------|-----------|-------------------|
|项目模板|类型的项目中可用**新项目**对话框。|<ul><li>F # 应用程序<br /></li><li>F # 库<br /></li><li>F # 教程<br /></li><li>F # 可移植库<br /></li><ul/>|
|项模板|文件中的可用类型**添加新项**对话框。|<ul><li>F # 源代码文件 (.fs)<br /></li><li>F # 脚本 (.fsx)<br /></li><li>F # 签名文件 (.fsi)<br /></li><li>配置文件 (.config)<br /></li><li>SQL 数据库连接 （LINQ SQL 类型提供程序）<br /></li><li>SQL 数据库连接 (LINQ to Entities 类型提供程序)<br /></li><li>OData 服务连接 （LINQ 类型提供程序）<br /></li><li>WSDL 服务连接 （类型提供程序）<br /></li><li>XML 文件 (.xml)<br /></li><li>文本文件<br /></li><ul/>|
若要创建的应用程序可以作为独立的可执行文件运行，选择 F # 应用程序项目类型。 若要创建库 (即，托管程序集或。DLL 文件） 用于 Windows 桌面平台上，选择 F # 库。 若要创建的可移植库，可以使用任何受支持的平台上，选择 F # 可移植运行库。 F # 可移植运行库项目引用的是适用于创建可以用于在例如 Windows 应用商店应用，.NET Framework 4.5、 Xamarin.iOS 和 Xamarin.Android 的平台运行的应用程序的 F # 库 FSharp.Core.dll 的版本。

有关数据访问的项模板的详细信息，请参阅[类型提供程序](../tutorials/type-providers/index.md)。

下表总结了支持的和不支持 F # 中的项目属性功能。 有关详细信息，请参阅[配置项目](configuring-projects.md)和[项目设计器简介](https://msdn.microsoft.com/library/898dd854-c98d-430c-ba1b-a913ce3c73d7)。

|项目设置|F # 中支持？|备注|
|---------------|----------------|-----|
|资源文件|是||
|生成、 调试和引用设置|是||
|多目标|是||
|图标和清单|No|可通过编译器命令行选项。|
|ASP.NET 客户端服务|No||
|ClickOnce|No|如果适用，请在另一个.NET Framework 语言中，使用客户端项目。|
|强命名|No|可通过编译器命令行选项。|
|发布的程序集和版本管理|No||
|代码分析|No|手动或作为后期生成命令的一部分，可以运行代码分析工具。|
|安全 （更改信任级别）|No||

## <a name="code-and-text-editor-features"></a>代码和文本编辑器功能
F # 中支持以下功能的 Visual Studiocode 和文本编辑器。 有关在 Visual Studio 中和功能的文本编辑器中编辑代码的常规信息，请参阅[在代码和文本编辑器中编写代码](/visualstudio/ide/writing-code-in-the-code-and-text-editor)。

|功能|描述|F # 中支持？|
|-------|-----------|----------------|
|自动注释|可注释或取消注释的代码部分。|是|
|自动设置格式|重新格式化使用标准的缩进和样式的代码。|No|
|书签|使用此选项可在编辑器中保存位置。|是|
|更改缩进|缩进或取消对选定的行。|是|
|[查找和替换文本](/visualstudio/ide/finding-and-replacing-text)|可以在文件、 项目或解决方案中，搜索并可能将更改文本。|是|
|转到.NET Framework API 的定义|当将光标置于.NET Framework API 时，将显示从.NET Framework 元数据生成的代码。|No|
|转到用户定义的 API 的定义|当光标位于你定义，将光标移到代码中的位置，其中定义实体的程序实体上。|是|
|转到行|使用此选项可转到在文件中，按行号的特定行。|是|
|在文件顶部导航栏|可以通过跳到代码中的位置，例如，函数名称。|是|
|大纲显示。 请参阅[大纲显示](/visualstudio/ide/outlining)。|使用此选项可折叠的代码来创建更紧凑视图的部分。|是|
|为制表符|将空间转换为选项卡。|是|
|类型着色|显示定义特殊的颜色的颜色的类型名称。|是|
|快速查找。 请参阅快速查找，查找和替换窗口。|可用于搜索文件或项目中。|是|

## <a name="intellisense-features"></a>IntelliSense 功能
下表总结了支持的和不支持 F # 中的 IntelliSense 功能。 Intellisense 的常规信息，请参阅[使用 IntelliSense](/visualstudio/ide/using-intellisense)。

|功能|描述|F # 中支持？|
|-------|-----------|----------------|
|自动实现接口|生成为接口方法的代码存根 （stub）。|No|
|代码片段|常见的编码构造的库中的代码注入主题。|No|
|完成单词|通过完成单词和名称，键入时键入的节省。|是|
|使用第一个完成模式|启用时，可使 word 完成功能选择第一个匹配项，当你键入时，而不是等待你选择一个或按**CTRL + SPACE**。|No|
|生成代码元素|使您能够生成各种构造的存根 （stub） 代码。|No|
|列表成员|当你键入成员访问运算符 （.） 时，显示类型的成员。|是|
|组织 Using / 打开|将引用的命名空间组织**使用**C# 中的语句或**打开**F # 中的指令。|No|
|参数信息|键入函数调用时，将显示有关参数的有用信息。|是|
|快速信息|显示代码中的任何标识符的完整声明。|是|
在 Visual Studio 2012 不支持 F # 代码的重构。

## <a name="debugging-features"></a>调试功能
下表总结了在调试 F # 代码时可用的功能。 有关 Visual Studio 调试器的常规信息，请参阅[Visual Studio 中调试](https://msdn.microsoft.com/library/sc65sadd.aspx)。

|功能|描述|F # 中支持？|
|-------|-----------|----------------|
|“自动”窗口|显示自动或临时变量。|No|
|断点|可让您暂停在特定点上的在调试过程中执行代码。|是|
|条件断点|启用测试条件，用于确定是否应暂停执行的断点。|是|
|编辑并继续|使代码可以修改和编译期间不必停止再重新启动调试器调试正在运行的程序。|No|
|表达式计算器|计算，并在运行时中执行代码。|否，但 C# 可以使用表达式计算器，尽管你必须使用 C# 语法。|
|历史调试|使用此选项可单步执行之前执行的代码。|是|
|局部变量窗口|显示本地定义的值和变量。|是|
|运行到光标处|使用此选项可执行代码，直到达到所包含光标的行。|是|
|逐语句|使您能够向前执行，并将移动到任何函数调用。|是|
|逐过程|可向前当前堆栈帧中的执行，并跳过任何函数调用。|是|

## <a name="additional-tools"></a>其他工具
下表总结了 F # 在 Visual Studio 工具的支持。

|工具|描述|F # 中支持？|
|----|-----------|----------------|
|调用层次结构|显示在代码中调用函数的嵌套的结构。|No|
|代码度量|收集有关你的代码，如行计数信息。|No|
|类视图|提供基于类型的项目中的代码视图。|No|
|[“错误列表”窗口](/visualstudio/ide/reference/error-list-window)|在代码中显示错误的列表。|是|
|[F# Interactive](../tutorials/fsharp-interactive/index.md)|使你能够键入 （或复制和粘贴） F # 代码并独立于你的项目的生成立即运行它。 F # Interactive 窗口是读取、 计算、 打印循环 (REPL)。|是|
|对象浏览器|使用此选项可查看的程序集中的类型。|F # 类型在编译的程序集中显示不显示您创作的样子。 你可以浏览的已编译的表示形式 F # 类型，但无法查看的类型，因为它们从 F # 显示。|
|[输出窗口](/visualstudio/ide/reference/output-window)|显示生成输出。|是|
|性能分析|提供用于测量你的代码的性能工具。|是|
|“属性”窗口|显示并允许在具有焦点的开发环境中对象的属性的编辑。|是|
|[服务器资源管理器](https://msdn.microsoft.com/library/x603htbk.aspx)|提供了与各种服务器资源进行交互的方式。|是|
|解决方案资源管理器|可以查看和管理项目和文件。|是|
|任务列表|使您能够管理与你的代码相关的工作项。|是|
|测试项目|提供功能，可帮助你测试代码。|No|
|工具箱|显示包含可拖动的对象，如控件和主要部分的文本或代码的选项卡。|是|

## <a name="see-also"></a>另请参阅
 [要开始使用 Visual Studio 中的 F #](../get-started/get-started-visual-studio.md)  
 [配置项目](configuring-projects.md)  
