---
title: "F# Interactive 选项"
description: "了解有关 F # Interactive，支持的命令行选项 fsi.exe。"
keywords: "visual f#, f#, 函数编程"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: f9f3e39b-ce6c-41ff-991f-0625f46441ae
ms.openlocfilehash: 0fc369993b3ee4c8a9139e4a365330197fe66946
ms.sourcegitcommit: cf22b29db780e532e1090c6e755aa52d28273fa6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/01/2018
---
# <a name="f-interactive-options"></a>F# Interactive 选项

> [!NOTE]
本文目前仅介绍适用于 Windows 的体验。  它将被重写。

本主题介绍 F # Interactive，支持的命令行选项`fsi.exe`。 F # Interactive 接受许多 F # 编译器，与相同的命令行选项，但还接受一些附加选项。

## <a name="using-f-interactive-for-scripting"></a>使用 F # Interactive 用于脚本编写
F # Interactive， `fsi.exe`、 以交互方式，可启动或从命令行运行脚本可启动它。 命令行语法

```
> fsi.exe [options] [ script-file [arguments] ]
```

F # 脚本文件的文件扩展名是`.fsx`。

## <a name="table-of-f-interactive-options"></a>F # Interactive 选项的表
下表总结了所支持的 F # Interactive 选项。 在命令行上或通过 Visual Studio IDE，你可以设置这些选项。 若要在 Visual Studio IDE 中设置这些选项，打开**工具**菜单上，选择**选项...**，然后展开**F # 工具**节点，然后选择**F # Interactive**。

其中列表出现在 F # Interactive 选项自变量，用分号分隔列表元素 (`;`)。

|选项|描述|
|------|-----------|
|**--**|用于指示 F # Interactive 对 F # 程序或脚本，你可以在代码中使用访问列表作为命令行自变量视为其余的自变量**fsi.CommandLineArgs**。|
|**--checked**[**+**&#124;**-**]|与相同**fsc.exe**编译器选项。 有关详细信息，请参阅[编译器选项](compiler-options.md)。|
|**--codepage:&lt;int&gt;**|与相同**fsc.exe**编译器选项。 有关详细信息，请参阅[编译器选项](compiler-options.md)。|
|**--crossoptimize**[**+**&#124;**-**]|启用或禁用跨模块优化。|
|**--debug**[**+**&#124;**-**]<br /><br />**--debug:**[**full**&#124;**pdbonly**]<br /><br />**-g**[**+**&#124;**-**]<br /><br />**-g:**[**full**&#124;**pdbonly**]|与相同**fsc.exe**编译器选项。 有关详细信息，请参阅[编译器选项](compiler-options.md)。|
|**--define:&lt;string&gt;**|与相同**fsc.exe**编译器选项。 有关详细信息，请参阅[编译器选项](compiler-options.md)。|
|**--exec**|指示 F # interactive 加载文件或运行命令行上给出的脚本文件后退出。|
|**--fullpaths**|与相同**fsc.exe**编译器选项。 有关详细信息，请参阅[编译器选项](compiler-options.md)。|
|**--gui**[**+**&#124;**-**]|启用或禁用 Windows 窗体事件循环。 默认为已启用。|
|**--help**<br /><br />**-?**|用于显示的命令行语法和每个选项的简短说明。|
|**--lib:&lt;folder-list&gt;**<br /><br />**-I:&lt;folder-list&gt;**|与相同**fsc.exe**编译器选项。 有关详细信息，请参阅[编译器选项](compiler-options.md)。|
|**--load:&lt;filename&gt;**|将在启动时给定的源代码编译并将已编译的 F # 构造加载到会话。 如果目标源包含脚本的指令，例如**#use**或**#load**，则必须使用**-使用**或**#use**而不是**-加载**或**#load**。|
|**--mlcompatibility**|与相同**fsc.exe**编译器选项。 有关详细信息，请参阅[编译器选项](compiler-options.md)。|
|**--noframework**|与相同**fsc.exe**编译器选项。 有关详细信息，请参阅[编译器选项](compiler-options.md)|
|**--nologo**|与相同**fsc.exe**编译器选项。 有关详细信息，请参阅[编译器选项](compiler-options.md)。|
|**--nowarn:&lt;warning-list&gt;**|与相同**fsc.exe**编译器选项。 有关详细信息，请参阅[编译器选项](compiler-options.md)。|
|**--optimize**[**+**&#124;**-**]|与相同**fsc.exe**编译器选项。 有关详细信息，请参阅[编译器选项](compiler-options.md)。|
|**--preferreduilang:&lt;lang&gt;**| 指定首选的输出语言区域性名称 （例如，ES-ES、 JA-JP）。 |
|**--quiet**|禁止显示 F # Interactive 的输出到**stdout**流。|
|**--quotations-debug**|指定应从 F # 引号文本派生，并反映定义的表达式发出额外的调试信息。 调试信息添加到 F # 表达式树节点的自定义属性。 请参阅[代码引用](code-quotations.md)和[Expr.CustomAttributes](https://msdn.microsoft.com/library/eb89943f-5f5b-474e-b125-030ca412edb3)。|
|**--readline**[**+**&#124;**-**]|启用或禁用在交互模式中的 tab 自动补全。|
|**--reference:&lt;filename&gt;**<br /><br />**-r:&lt;filename&gt;**|与相同**fsc.exe**编译器选项。 有关详细信息，请参阅[编译器选项](compiler-options.md)。|
|**--tailcalls**[**+**&#124;**-**]|启用或禁用的结尾 IL 指令，这会导致堆栈帧要重用为尾递归函数使用。 默认情况下会启用此选项。|
|**--use:&lt;filename&gt;**|告知解释程序以使用上启动的给定的文件作为初始的输入。|
|**--utf8output**|Fsc.exe 编译器选项相同。 有关详细信息，请参阅[编译器选项](compiler-options.md)。|
|**--warn:&lt;warning-level&gt;**|与相同**fsc.exe**编译器选项。 有关详细信息，请参阅[编译器选项](compiler-options.md)。|
|**--warnaserror**[**+**&#124;**-**]|与相同**fsc.exe**编译器选项。 有关详细信息，请参阅[编译器选项](compiler-options.md)。|
|**--warnaserror**[**+**&#124;**-**]:**&lt;int-list&gt;**|与相同**fsc.exe**编译器选项。 有关详细信息，请参阅[编译器选项](compiler-options.md)。|

## <a name="related-topics"></a>相关主题

|标题|描述|
|-----|-----------|
|[编译器选项](compiler-options.md)|描述 F # 编译器，可用的命令行选项**fsc.exe**。|
