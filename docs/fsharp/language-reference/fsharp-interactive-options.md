---
title: F# Interactive 选项
description: 了解F#交互式 fsi.exe 支持的命令行选项。
ms.date: 05/16/2016
ms.openlocfilehash: c9cd5c2e73a6e2f6ce0a9b2f2a631b6a2658423c
ms.sourcegitcommit: a2d0e1f66367367065bc8dc0dde488ab536da73f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/18/2019
ms.locfileid: "71083123"
---
# <a name="f-interactive-options"></a>F# Interactive 选项

> [!NOTE]
> 本文目前仅介绍适用于 Windows 的体验。  它将被重写。

本主题介绍F#交互式`fsi.exe`支持的命令行选项。 F#交互式接受许多与F#编译器相同的命令行选项，但也接受一些其他选项。

## <a name="using-f-interactive-for-scripting"></a>使用F#交互式脚本编写
F#交互式、 `fsi.exe`可以交互方式启动，也可以从命令行启动以运行脚本。 命令行语法为

```console
> fsi.exe [options] [ script-file [arguments] ]
```

F#脚本文件的文件扩展名为`.fsx`。

## <a name="table-of-f-interactive-options"></a>F#交互式选项表
下表总结了F#交互式支持的选项。 可以在命令行上或通过 Visual Studio IDE 设置这些选项。 若要在 Visual Studio IDE 中设置这些选项，请打开 "**工具**" 菜单，选择 "**选项 ...** "，然后展开 "  **F#工具**" 节点，然后选择 **F# "交互式**"。

其中列表显示在F#交互式选项参数中，列表元素用分号（`;`）分隔。

|选项|描述|
|------|-----------|
|**--**|用于指示F# Interactive 将其余参数视为程序或脚本的F#命令行参数，您可以使用**fsi.exe. my.application.commandlineargs**的代码来访问这些参数。|
|**--checked**[ **+** &#124; **-** ]|与**fsc.exe**编译器选项相同。 有关详细信息，请参阅[编译器选项](compiler-options.md)。|
|**--codepage:&lt;int&gt;**|与**fsc.exe**编译器选项相同。 有关详细信息，请参阅[编译器选项](compiler-options.md)。|
|**--consolecolors**[ **+** &#124; **-** ]|输出警告和错误消息的颜色。|
|**--crossoptimize**[ **+** &#124; **-** ]|启用或禁用跨模块优化。|
|**--debug**[ **+** &#124; **-** ]<br /><br />**--debug:** [**full**&#124;**pdbonly**&#124;**portable**&#124;**embedded**]<br /><br />**-g**[ **+** &#124; **-** ]<br /><br />**-g:** [**full**&#124;**pdbonly**&#124;**portable**&#124;**embedded**]|与**fsc.exe**编译器选项相同。 有关详细信息，请参阅[编译器选项](compiler-options.md)。|
|**--define:&lt;string&gt;**|与**fsc.exe**编译器选项相同。 有关详细信息，请参阅[编译器选项](compiler-options.md)。|
|**--deterministic**[ **+** &#124; **-** ]|生成一个确定性程序集（包括模块版本 GUID 和时间戳）。|
|**--exec**|指示F#在加载文件或运行命令行上给定的脚本文件后退出 interactive。|
|**--fullpaths**|与**fsc.exe**编译器选项相同。 有关详细信息，请参阅[编译器选项](compiler-options.md)。|
|**--gui**[ **+** &#124; **-** ]|启用或禁用 Windows 窗体事件循环。 默认为已启用。|
|**--help**<br /><br />**-?**|用于显示命令行语法和每个选项的简短说明。|
|**--lib：&lt;文件夹-列表&gt;**<br /><br />**-I：&lt;文件夹列表&gt;**|与**fsc.exe**编译器选项相同。 有关详细信息，请参阅[编译器选项](compiler-options.md)。|
|**--load：&lt;filename&gt;**|在启动时编译给定的源代码，并将编译F#的构造加载到会话中。 如果目标源包含脚本指令（如 **#use**或 **#load**），则必须使用 **--use**或 **#use** ，而不是 **--load**或 **#load**。|
|**--mlcompatibility**|与**fsc.exe**编译器选项相同。 有关详细信息，请参阅[编译器选项](compiler-options.md)。|
|**--noframework**|与**fsc.exe**编译器选项相同。 有关详细信息，请参阅[编译器选项](compiler-options.md)|
|**--nologo**|与**fsc.exe**编译器选项相同。 有关详细信息，请参阅[编译器选项](compiler-options.md)。|
|**--nowarn：&lt;warning-list&gt;**|与**fsc.exe**编译器选项相同。 有关详细信息，请参阅[编译器选项](compiler-options.md)。|
|**--optimize**[ **+** &#124; **-** ]|与**fsc.exe**编译器选项相同。 有关详细信息，请参阅[编译器选项](compiler-options.md)。|
|**--preferreduilang:&lt;lang&gt;**| 指定首选输出语言区域性名称（例如，es，ja-jp）。 |
|**--quiet**|禁止F#交互式输出到**stdout**流。|
|**--quotations-debug**|指定应为从F#引号文本和反射定义派生的表达式发出额外的调试信息。 调试信息将添加到F#表达式树节点的自定义属性中。 请参阅[代码引用](code-quotations.md)和[CustomAttributes](https://msdn.microsoft.com/library/eb89943f-5f5b-474e-b125-030ca412edb3)。|
|**--readline**[ **+** &#124; **-** ]|启用或禁用交互模式下的 tab 自动补全。|
|**--reference：&lt;filename&gt;**<br /><br />**-r：&lt;filename&gt;**|与**fsc.exe**编译器选项相同。 有关详细信息，请参阅[编译器选项](compiler-options.md)。|
|**--shadowcopyreferences**[ **+** &#124; **-** ]|禁止F#交互进程锁定引用。|
|**--simpleresolution**|使用基于目录的规则而不是 MSBuild 解析来解析程序集引用。|
|**--tailcalls**[ **+** &#124; **-** ]|启用或禁用 tail IL 指令，这将导致为尾递归函数重用堆栈帧。 默认情况下会启用此选项。|
|**--targetprofile：&lt;string&gt;**|指定此程序集的目标框架配置文件。 有效值为 mscorlib、netcore 或 netstandard。  默认值为 mscorlib。|
|**--use：&lt;filename&gt;**|通知解释器在启动时使用给定文件作为初始输入。|
|**--utf8output**|与 fsc.exe 编译器选项相同。 有关详细信息，请参阅[编译器选项](compiler-options.md)。|
|**--warning：&lt;警告级别&gt;**|与**fsc.exe**编译器选项相同。 有关详细信息，请参阅[编译器选项](compiler-options.md)。|
|**--warnaserror**[ **+** &#124; **-** ]|与**fsc.exe**编译器选项相同。 有关详细信息，请参阅[编译器选项](compiler-options.md)。|
|**--warnaserror**[ **+** &#124; **-** ]: **&lt;int-list&gt;**|与**fsc.exe**编译器选项相同。 有关详细信息，请参阅[编译器选项](compiler-options.md)。|

## <a name="related-topics"></a>相关主题

|Title|描述|
|-----|-----------|
|[编译器选项](compiler-options.md)|介绍适用于F#编译器**fsc.exe**的命令行选项。|
