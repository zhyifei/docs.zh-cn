---
title: 编译器选项 (F#)
description: 使用F#编译器命令行选项来控制编译的应用F#应用程序和库。
ms.date: 05/16/2016
ms.openlocfilehash: f4a596d0dede6f66faa34374f7f73a89323f1620
ms.sourcegitcommit: db8b83057d052c1f9f249d128b08d4423af0f7c2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/02/2018
ms.locfileid: "33566439"
---
# <a name="compiler-options"></a>编译器选项

本主题介绍有关编译器命令行选项F#编译器、 fsc.exe。 此外可以通过设置项目属性控制编译环境。


## <a name="compiler-options-listed-alphabetically"></a>按字母顺序列出的编译器选项
下表显示了按字母顺序列出的编译器选项。 某些F#编译器选项都类似于C#编译器选项。 如果出现这种情况，一个指向C#编译器选项主题提供。



|编译器选项|描述|
|---------------|-----------|
|**-a****&lt;输出文件名&gt;**|生成一个库，并指定其文件名。 此选项是一种短形式 **-目标： 库****&lt;filename&gt;**。|
|**--baseaddress:&lt;string&gt;**|指定要生成库的基址。<br /><br />此编译器选项等效于C#具有相同名称的编译器选项。 有关详细信息，请参阅[ &#47;baseaddress &#40;C&#35;编译器选项&#41;](https://msdn.microsoft.com/library/2fdbz5xd.aspx)。|
|**--codepage:&lt;int&gt;**|指定用于读取源文件的代码页。<br /><br />此编译器选项等效于C#具有相同名称的编译器选项。 有关详细信息，请参阅[&#47;代码页&#40;C&#35;编译器选项&#41;](https://msdn.microsoft.com/library/w0kyekyh.aspx)。|
|**--consolecolors**|指定错误和警告的控制台上使用彩色编码的文本。|
|**--crossoptimize**[**+**&#124;**-**]|启用或禁用跨模块优化。|
|**--delaysign**[**+**&#124;**-**]|延迟签名程序集使用仅强名称密钥的公共部分。<br /><br />此编译器选项等效于C#具有相同名称的编译器选项。 有关详细信息，请参阅[ &#47;delaysign &#40;C&#35;编译器选项&#41;](https://msdn.microsoft.com/library/ta1sxwy8.aspx)。|
|**--checked**[**+**&#124;**-**]|启用或禁用溢出检查的生成。<br /><br />此编译器选项等效于C#具有相同名称的编译器选项。 有关详细信息，请参阅[&#47;检查&#40;C&#35;编译器选项&#41;](https://msdn.microsoft.com/library/h25wtyxf.aspx)。|
|**--debug**[**+**&#124;**-**]<br /><br />**-g**[**+**&#124;**-**]<br /><br />**--debug**:[**full**&#124;**pdbonly**]<br /><br />**-g:** [**full**&#124;**pdbonly**]|启用或禁用生成调试信息或指定要生成的类型。 默认值为 full，允许附加到正在运行的程序。 选择**pdbonly**获取有限的 pdb （程序数据库） 文件中存储的调试信息。<br /><br />等效于C#具有相同名称的编译器选项。 有关详细信息，请参见<br /><br />[&#47;调试&#40;C&#35;编译器选项&#41;](https://msdn.microsoft.com/library/8cw0bt21.aspx)。|
|**--define:&lt;string&gt;**<br /><br />**-d:&lt;string&gt;**|定义条件编译中使用的符号。|
|**--deterministic**[**+**&#124;**-**]|生成确定性程序集 （包括模块版本 GUID 以及时间戳）。  这不能用于通配符的版本号，并仅支持嵌入和可移植调试类型|
|**--doc:&lt;xmldoc-filename&gt;**|指示编译器生成 XML 文档注释指定的文件。 有关更多信息，请参见 [XML Documentation](xml-documentation.md)。<br /><br />此编译器选项等效于C#具有相同名称的编译器选项。 有关详细信息，请参阅[&#47;文档&#40;C&#35;编译器选项&#41;](https://msdn.microsoft.com/library/3260k4x7.aspx)。|
|**--fullpaths**|指示编译器生成完全限定的路径。<br /><br />此编译器选项等效于C#具有相同名称的编译器选项。 有关详细信息，请参阅[ &#47;fullpaths &#40;C&#35;编译器选项&#41;](https://msdn.microsoft.com/library/d315xc66.aspx)。|
|**--help**<br /><br />**-?**|显示用法信息，包括所有编译器选项的简短说明。|
|**--highentropyva**[**+**&#124;**-**]|启用或禁用高熵地址空间布局随机化 (ASLR) 增强的安全功能。 操作系统随机化内存中加载应用程序 （例如堆栈和堆） 的基础结构的位置的位置。 如果启用此选项，操作系统可以使用此随机化以在 64 位计算机上使用完整 64 位地址空间。|
|**--keycontainer:&lt;string&gt;**|指定强名称密钥容器。|
|**--keyfile:&lt;filename&gt;**|指定生成的程序集进行签名的公钥文件的名称。|
|**--lib:&lt;folder-name&gt;**<br /><br />**-I:&lt;文件夹名称&gt;**|指定要在其中搜索引用程序集的目录。<br /><br />此编译器选项等效于C#具有相同名称的编译器选项。 有关详细信息，请参阅[ &#47;lib &#40;C&#35;编译器选项&#41;](https://msdn.microsoft.com/library/s5bac5fx.aspx)。|
|**--linkresource**:**&lt;resource-info&gt;**|指定的资源链接到该程序集。 资源信息的格式*文件名*[，*名称*[，*公共*&#124;*专用*]]<br /><br />链接具有此选项的单个资源是嵌入整个资源文件的替代方法 **-资源**选项。<br /><br />此编译器选项等效于C#具有相同名称的编译器选项。 有关详细信息，请参阅[ &#47;linkresource &#40;C&#35;编译器选项&#41;](https://msdn.microsoft.com/library/xawyf94k.aspx)。|
|**--mlcompatibility**|将忽略所设计的功能用于与其他版本的 ML 兼容性时，将显示警告。|
|**--noframework**|禁用对.NET Framework 程序集的默认引用。|
|**--nointerfacedata**|指示编译器省略其通常向包含程序集的资源F#的特定元数据。|
|**--nologo**|在启动编译器时，不会显示横幅文本。|
|**--nooptimizationdata**|指示编译器将只包括所必需的实现内联的构造优化。 禁止跨模块内联，但会提高二进制兼容性。|
|**--nowin32manifest**|指示编译器省略默认的 Win32 清单。|
|**--nowarn:&lt;int-list&gt;**|禁用按编号列出的特定警告。 用逗号分隔每个警告编号。 可以发现从编译输出的任何警告的警告编号。<br /><br />此编译器选项等效于C#具有相同名称的编译器选项。 有关详细信息，请参阅[ &#47;nowarn &#40;C&#35;编译器选项&#41;](https://msdn.microsoft.com/library/7f28x9z3.aspx)。|
|**--optimize**[**+**&#124;**-**]**[&lt;string-list&gt;]**<br /><br />**-O[+&#124;-] [&lt;string-list&gt;]**|启用或禁用优化。 一些优化选项可以禁用或有选择地启用通过列出它们。 这些是： **nojitoptimize**， **nojittracking**， **nolocaloptimize**， **nocrossoptimize**， **notailcalls**.|
|**--out:&lt;output-filename&gt;**<br /><br />**-o:&lt;output-filename&gt;**|指定编译的程序集或模块的名称。<br /><br />此编译器选项等效于C#具有相同名称的编译器选项。 有关详细信息，请参阅[ &#47;out &#40;C&#35;编译器选项&#41;](https://msdn.microsoft.com/library/bw3t50f3.aspx)。|
|**--pdb:&lt;pdb-filename&gt;**|命名的输出调试 PDB （程序数据库） 文件。 时，此选项才适用 **-调试**还启用了。<br /><br />此编译器选项等效于C#具有相同名称的编译器选项。 有关详细信息，请参阅[ &#47;pdb &#40;C&#35;编译器选项&#41;](https://msdn.microsoft.com/library/ms228625.aspx)。|
|**-平台：&lt;平台名称&gt;**|指定生成的代码仅将在指定的平台上运行 (**x86**， **Itanium**，或**x64**)，或者，如果平台名称**anycpu**选择，指定生成的代码可以在任何平台上运行。<br /><br />此编译器选项等效于C#具有相同名称的编译器选项。 有关详细信息，请参阅[&#47;平台&#40;C&#35;编译器选项&#41;](https://msdn.microsoft.com/library/zekwfyz4.aspx)。|
|**--preferreduilang:&lt;lang&gt;**| 指定首选的输出语言区域性名称 （例如，ES-ES，JA-JP）。 |
|**--quotations-debug**|指定应派生自的表达式发出额外的调试信息F#的报价文本和反射的定义。 调试信息添加到自定义属性的F#表达式树节点。 请参阅[代码引用](code-quotations.md)并[Expr.CustomAttributes](https://msdn.microsoft.com/library/eb89943f-5f5b-474e-b125-030ca412edb3)。|
|**--reference:&lt;assembly-filename&gt;**<br /><br />**-r** &lt;**assembly-filename&gt;**|使代码从F#或.NET Framework 程序集供正在编译的代码。<br /><br />此编译器选项等效于C#具有相同名称的编译器选项。 有关详细信息，请参阅[&#47;引用&#40;C&#35;编译器选项&#41;](https://msdn.microsoft.com/library/yabyz3h4.aspx)。|
|**--resource:&lt;resource-filename&gt;**|将托管的资源文件嵌入到生成的程序集。<br /><br />此编译器选项等效于C#具有相同名称的编译器选项。 有关详细信息，请参阅[&#47;资源&#40;C&#35;编译器选项&#41;](https://msdn.microsoft.com/library/c0tyye07.aspx)。|
|**--sig**:&lt;**signature-filename&gt;**|生成基于生成的程序集的签名文件。 有关签名文件的详细信息，请参阅[签名](signatures.md)。|
|**--simpleresolution**|指定应使用基于目录的 Mono 规则而不是 MSBuild 解析解析程序集引用。 默认值是使用 MSBuild 解析，但在 Mono 下运行时例外。|
|**--standalone**|指定生成的程序集，包括所有依赖项使情况下独立运行而无需其他程序集，如F#库。|
|**--staticlink:&lt;assembly-name**&gt;|以静态方式链接给定的程序集和依赖于此程序集的所有引用的 Dll。 使用程序集名称，而不是 DLL 名称。|
|**--subsystemversion**|指定用于生成可执行文件的操作系统子系统的版本。 将 6.02 用于 Windows 8.1，6.01 用于 Windows 7，6.00 用于 Windows Vista。 此选项仅适用于可执行文件，而非 Dll，并且如果应用程序依赖于仅在某些版本的操作系统上可用的特定安全功能才需要使用。 如果使用此选项，并且用户尝试在较低版本的操作系统上执行应用程序，它将失败并显示错误消息。|
|**--tailcalls**[**+**&#124;**-**]|启用或禁用使用，尾 IL 指令将使得为尾递归函数重用堆栈帧。 默认情况下会启用此选项。|
|**--target**:[**exe** &#124; **winexe** &#124; **library** &#124; **module** ] **&lt;output-filename&gt;**|指定生成的已编译代码的类型和文件。<ul><li>**exe**意味着一个控制台应用程序。<br /></li><li>**winexe**意味着不同于控制台应用程序，它不具有标准输入/输出流 （stdin、 stdout 和 stderr） 定义的 Windows 应用程序。<br /></li><li>**库**是程序集没有入口点。<br /></li><li>**模块**是.NET Framework 模块 (.netmodule)，它可以更高版本结合，与其他模块到程序集。<br /></li><ul/>此编译器选项等效于C#具有相同名称的编译器选项。 有关详细信息，请参阅[&#47;目标&#40;C&#35;编译器选项&#41;](https://msdn.microsoft.com/library/6h25dztx.aspx)。|
|**--times**|显示编译的计时信息。|
|**--utf8output**|启用打印编译器输出中的 utf-8 编码。|
|**-警告：&lt;警告级别&gt;**|设置警告等级 (0 到 5)。 默认级别为 3。 每个警告给定一个根据其严重性等级。 级别 5 程度在等级 1 提供更多，但更少的严重警告。<br /><br />5 级警告是： 21 （在运行时检查递归使用），22 (**let rec**评估的顺序紊乱)，45 （完全的抽象） 和 52 （防御性副本）。 所有其他警告是级别 2。<br /><br />此编译器选项等效于C#具有相同名称的编译器选项。 有关详细信息，请参阅[ &#47;，则发出警告&#40;C&#35;编译器选项&#41;](https://msdn.microsoft.com/library/13b90fz7.aspx)。|
|**--warnon:&lt;int-list&gt;**|启用默认情况下可能处于关闭状态，或通过另一个命令行选项禁用特定警告。 在F#3.0 中，只有 1182 （未使用的变量） 警告默认处于关闭状态。|
|**--warnaserror**[**+**&#124;**-**] [**&lt;int-list&gt;**]|启用或禁用警告报告为错误的选项。 你可以提供特定的警告编号，若要禁用或启用。 更高版本中命令行选项重写前面的命令行选项。 例如，若要指定不想报告为错误的警告，请指定 **-warnaserror +-warnaserror-:&lt;int 列表&gt;**。<br /><br />此编译器选项等效于C#具有相同名称的编译器选项。 有关详细信息，请参阅[ &#47;warnaserror &#40;C&#35;编译器选项&#41;](https://msdn.microsoft.com/library/406xhdz3.aspx)。|
|**--win32manifest:manifest-filename**|将 Win32 清单文件添加到编译。 此编译器选项等效于C#具有相同名称的编译器选项。 有关详细信息，请参阅[ &#47;win32manifest &#40;C&#35;编译器选项&#41;](https://msdn.microsoft.com/library/bb545961.aspx)。|
|**--win32res:resource-filename**|将 Win32 资源文件添加到编译。<br /><br />此编译器选项等效于C#具有相同名称的编译器选项。 有关详细信息，请参阅[ &#47;win32res (&#40;c&#35);编译器选项&#41;](https://msdn.microsoft.com/library/8f2f5x2e.aspx)。|

## <a name="related-topics"></a>相关主题


|标题|描述|
|-----|-----------|
|[F# Interactive 选项](fsharp-interactive-options.md)|介绍支持的命令行选项F#解释器、 fsi.exe。|
|[项目属性引用](/visualstudio/ide/reference/project-properties-reference)|介绍了项目，包括提供生成选项的项目属性页的 UI。|
