---
title: 如何：确定已安装的 .NET Framework 版本
ms.date: 02/20/2019
dev_langs:
- csharp
- vb
ms.custom: updateeachrelease
helpviewer_keywords:
- versions, determining for .NET Framework
- .NET Framework, determining version
ms.assetid: 40a67826-e4df-4f59-a651-d9eb0fdc755d
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d7661b3ebaa8f29d6d3b2adbc56c405c8f0945f3
ms.sourcegitcommit: 07c4368273b446555cb2c85397ea266b39d5fe50
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2019
ms.locfileid: "56584169"
---
# <a name="how-to-determine-which-net-framework-versions-are-installed"></a>如何：确定已安装的 .NET Framework 版本

用户可在他们的计算机上安装和运行 .NET Framework 的多个版本。 当你开发或部署应用时，你可能需要知道用户的计算机上安装了哪些 .NET Framework 版本。 请注意，.NET Framework 由两个采用不同版本的主要组件构成：  
  
- 一组程序集，它们是为应用提供功能的类型与资源的集合。 .NET Framework 和程序集使用相同的版本号。  
  
- 公共语言运行时 (CLR)，可管理并执行应用的代码。 CLR 由其自己的版本号标识（请参阅[版本和依赖关系](~/docs/framework/migration-guide/versions-and-dependencies.md)）。  
  
若要获取计算机上安装的 .NET Framework 版本的准确列表，你可以在代码中查看注册表或查询注册表：  
  
 [在注册表中查找 .NET Framework 版本 1-4](#net_a)  
 [在注册表中查找 .NET Framework 4.5 及更高版本](#net_b)  
 [使用代码查询注册表（版本 1-4）](#net_c)  
 [使用代码查询注册表（版本 4.5 和更高版本）](#net_d)  
 [使用 PowerShell 查询注册表（版本 4.5 及更高版本）](#ps_a)  

 若要查找 CLR 版本，你可以使用工具或代码：  
  
 [使用 Clrver 工具](#clr_a)  
 [使用代码查询 System.Environment 类](#clr_b)  

> [!NOTE]
> .NET Framework 版本和公共语言运行时 (CLR) 版本之间存在差异。 .NET Framework 基于构成 .Net Framework 类库的一组程序集进行版本控制。 例如，.NET Framework 版本包括 4.5、4.6.1 和 4.7.2。 CLR 基于执行 .NET Framework 应用程序的运行时进行版本控制，且单个 CLR 版本通常支持多个 .NET Framework 版本。 CLR 版本 4.30319.xxxxx 支持 .NET Framework 版本 4 到 4.5.2；CLR 版本 4.30319.42000 支持从 .NET Framework 4.6 开始的 .NET Framework 版本。 有关更多信息，请参见 <xref:System.Environment.Version?displayProperty=nameWithType> 属性。

 有关检测安装的每个 .NET Framework 版本的更新的信息，请参阅[如何：确定已安装的 .NET Framework 更新](~/docs/framework/migration-guide/how-to-determine-which-net-framework-updates-are-installed.md)。 若要了解如何安装 .NET Framework，请参阅[安装面向开发人员的 .NET Framework](../../../docs/framework/install/guide-for-developers.md)。  
  
<a name="net_a"></a>   
## <a name="find-net-framework-versions-1-4-in-the-registry"></a>在注册表中查找 .NET Framework 版本 1-4 
  
1.  在“开始”菜单上，选择“运行”。  
  
2.  在“打开”框中，输入“regedit.exe”。  
  
     你必须具有管理凭据才能运行 regedit.exe。  
  
3.  在注册表编辑器中，打开以下子项：  
  
     `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP`  
  
     对于 .NET Framework 版本 1.1 到 3.5，已安装的版本被列为 `NDP` 子项下的子项。 版本号存储在版本子项的“版本”项中。 
     
     对于 .NET Framework 4，“版本”项位于 `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4.0\Client` 子项和/或 `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4.0\Full` 子项下。

    > [!NOTE]
    > 注册表中的“NET Framework Setup”文件夹不会以句点开头。

    下图显示 .NET Framework 3.5 的子项及其“版本”项。

     ![.NET Framework 3.5 的注册表项。](../../../docs/framework/migration-guide/media/net-4-and-earlier.png ".NET Framework 4 及更早版本")

<a name="net_b"></a> 
## <a name="find-net-framework-versions-45-and-later-in-the-registry"></a>在注册表中查找 .NET Framework 4.5 及更高版本

1. 在“开始”菜单上，选择“运行”。

2. 在“打开”框中，输入“regedit.exe”。

     你必须具有管理凭据才能运行 regedit.exe。

3. 在注册表编辑器中，打开以下子项：

     `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\Full`

     请注意，`Full` 子项的路径包括 `Net Framework` 子项，而不包括 `.NET Framework`。

    > [!NOTE]
    > 如果 `Full` 子项不存在，则表示你尚未安装 .NET Framework 4.5 或更高版本。

     检查名为 `Release` 的 DWORD 值。 `Release` DWORD 的存在表明该计算机上已安装 .NET Framework 4.5 或更高版本。 其值是对应于特定版本的 .NET Framework 的版本键。 以下图为例，`Release` DWORD 的值为 378389，这是 .NET Framework 4.5 的版本密钥。 

     ![.NET Framework 4.5 的注册表项。](../../../docs/framework/migration-guide/media/clr-installdir.png "CLR_InstallDir")

下表列出每个 .NET Framework 版本 `Release` DWORD 的最小值。 可以使用这些值，如下所示：

- 若要确定是否存在 .NET Framework 最低版本，测试在注册表中找到的 `Release` DWORD 值是大于还是等于表中列出的值。 例如，如果应用程序需要 .NET Framework 4.7 或更高版本，则测试最小版本密钥值是否为 460798。

- 若要测试多个版本，请从最新的 .NET Framework 版本开始，然后对每个后续的早期版本进行测试。

[!INCLUDE[Release key values note](~/includes/version-keys-note.md)]

|.NET Framework 版本|Release DWORD 的值|
|--------------------------------|-------------|
|.NET Framework 4.5|378389|
|.NET Framework 4.5.1|378675|
|.NET Framework 4.5.2|379893|
|.NET Framework 4.6|393295|
|.NET Framework 4.6.1|394254|
|.NET Framework 4.6.2|394802|
|.NET Framework 4.7|460798|
|.NET Framework 4.7.1|461308|
|.NET Framework 4.7.2|461808|

有关完整的适用于特定 Windows 操作系统版本的 .NET Framework 的版本密钥表，请参阅 [.NET Framework 版本密钥和 Windows 操作系统版本](release-keys-and-os-versions.md)。

<a name="net_c"></a> 
## <a name="find-net-framework-versions-1-4-with-code"></a>使用代码查找 .NET Framework 版本 1-4

- 使用 <xref:Microsoft.Win32.RegistryKey?displayProperty=nameWithType> 类访问 Windows 注册表 `HKEY_LOCAL_MACHINE` 分支下的 `Software\Microsoft\NET Framework Setup\NDP\` 子项。

     下面的代码显示此查询的示例。

    > [!NOTE]
    > 此代码不演示如何检测 .NET Framework 4.5 或更高版本。 检查 `Release` DWORD 以检测这些版本，如上一节所述。 有关检测 .NET Framework 4.5 或更高版本的代码，请参阅本文的下一节。

     [!code-csharp[ListVersions](../../../samples/snippets/csharp/framework/migration-guide/versions-installed1.cs)]
     [!code-vb[ListVersions](../../../samples/snippets/visualbasic/framework/migration-guide/versions-installed1.vb)]

<a name="net_d"></a> 
## <a name="find-net-framework-versions-45-and-later-with-code"></a>使用代码查找 .NET Framework 4.5 及更高版本

1. `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\Full` 项中 `Release` DWORD 的存在表明该计算机上已安装 .NET Framework 4.5 或更高版本。 关键字的值表示已安装的版本。 若要检查此关键字，使用 <xref:Microsoft.Win32.RegistryKey.OpenBaseKey%2A?displayProperty=nameWithType> 和 <xref:Microsoft.Win32.RegistryKey.OpenSubKey%2A?displayProperty=nameWithType> 方法访问 Windows 注册表中的子项。

2. 检查 `Release` 关键字的值以确定安装的版本。 若要向前兼容，可以检查值是大于还是等于[在注册表中查找 .NET Framework 4.5 及更高版本](#net_b)部分的表中列出的值。

以下示例检查注册表中的 `Release` 值来确定是否已安装 .NET Framework 4.5 或更高版本。

[!code-csharp[ListVersions#5](../../../samples/snippets/csharp/framework/migration-guide/versions-installed3.cs)]
[!code-vb[ListVersions#5](../../../samples/snippets/visualbasic/framework/migration-guide/versions-installed3.vb)]

此示例遵循版本检查的建议做法：

- 检查 `Release` 项的值是否*大于等于*已知版本键的值。

- 按从最新版本到最早版本的顺序检查。

<a name="ps_a"></a> 
## <a name="check-for-a-minimum-required-net-framework-version-45-and-later-with-powershell"></a>使用 PowerShell 检查所需的 .NET Framework 的最低版本（4.5 或更高版本）

下面的示例检查 `Release` 关键字的值，以确定是否已安装 .NET Framework 4.6.2 或更高版本（如果已安装，返回 `True`；否则，返回 `False`）。

    ```PowerShell
    # PowerShell 5
    Get-ChildItem 'HKLM:\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\Full\' | Get-ItemPropertyValue -Name Release | Foreach-Object { $_ -ge 394802 } 
    ```

    ```PowerShell
    # PowerShell 4
    (Get-ItemProperty "HKLM:SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\Full").Release -gt 394802
    ```

    You can replace `394802` in the previous example with another value from the following table in the [Find .NET Framework versions 4.5 and later in the registry](#net_b) section to check for a different minimum required .NET Framework version.
  
<a name="clr_a"></a> 
## <a name="find-the-current-clr-version-with-clrverexe"></a>使用 Clrver.exe 查找当前的 CLR 版本

使用 CLR 版本工具 (Clrver.exe) 决定已安装在计算机上的公共语言运行时的版本。

从“Visual Studio 开发人员命令提示”，输入 `clrver`。 该命令生成类似下面的输出：

```console
Versions installed on the machine:
v2.0.50727
v4.0.30319
```

有关使用此工具的详细信息，请参阅 [Clrver.exe（CLR 版本工具）](~/docs/framework/tools/clrver-exe-clr-version-tool.md)。

<a name="clr_b"></a> 
## <a name="find-the-current-clr-version-with-the-environment-class"></a>使用 Environment 类查找当前的 CLR 版本

可以检索 <xref:System.Environment.Version?displayProperty=nameWithType> 属性的值，以检索标识当前正在执行代码的运行时版本的 <xref:System.Version> 对象。 此属性返回单个值，用于反映当前正在执行代码的运行时的版本；它不返回可能已安装在计算机上的程序集版本或运行时的其他版本。可以使用 <xref:System.Version.Major%2A?displayProperty=nameWithType> 属性获取主版本标识符（例如，“4”即表示版本 4.0），使用 <xref:System.Version.Minor%2A?displayProperty=nameWithType> 属性获取次要版本标识符（例如，“0”即表示版本 4.0），或使用 <xref:System.Version.ToString%2A?displayProperty=nameWithType> 方法获取完整版本字符串（例如，“4.0.30319.18010”，如以下代码所示）。 

对于 .NET Framework 版本 4、4.5、4.5.1 和 4.5.2，<xref:System.Environment.Version%2A?displayProperty=nameWithType> 属性返回字符串表现形式具有窗体 `4.0.30319.xxxxx` 的 <xref:System.Version> 对象。 对于 .NET Framework 4.6 及更高版本，形式为 `4.0.30319.42000`。

> [!IMPORTANT]
> 对于 .NET Framework 4.5 和更高版本，不建议使用 <xref:System.Environment.Version%2A?displayProperty=nameWithType> 属性来检测运行时的版本。 相反，我们建议查询注册表，如本文前面[通过用代码查询注册表来查找 .NET Framework 版本（.NET Framework 4.5 及更高版本）](#net_d)一节所述。

下面的示例已使用 <xref:System.Environment.Version%2A?displayProperty=nameWithType> 属性来检索运行时版本信息：

[!code-csharp[ListVersions](../../../samples/snippets/csharp/framework/migration-guide/versions-installed2.cs)]
[!code-vb[ListVersions](../../../samples/snippets/visualbasic/framework/migration-guide/versions-installed2.vb)]

## <a name="see-also"></a>请参阅

- [如何：确定已安装的 .NET Framework 更新](~/docs/framework/migration-guide/how-to-determine-which-net-framework-updates-are-installed.md)
- [安装面向开发者的 .NET Framework](../../../docs/framework/install/guide-for-developers.md)
- [版本和依赖关系](~/docs/framework/migration-guide/versions-and-dependencies.md)
