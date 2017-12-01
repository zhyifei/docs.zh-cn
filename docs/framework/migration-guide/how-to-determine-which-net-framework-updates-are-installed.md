---
title: "如何： 确定安装了哪些.NET Framework 安全更新和修补程序"
description: "了解如何确定在计算机上安装了哪些.NET Framework 安全更新和修补程序。"
ms.date: 11/21/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- updates, determining for .NET Framework
- .NET Framework, determining updates
ms.assetid: 53c7b5f7-d47a-402a-b194-7244a696a88b
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: c35705470a8e1b553eca2ca0c68d3b8b9b3f6fa6
ms.sourcegitcommit: a3ba258f7a8cab5c6d19a3743dd95e904ecebc44
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/27/2017
---
# <a name="how-to-determine-which-net-framework-security-updates-and-hotfixes-are-installed"></a>如何： 确定安装了哪些.NET Framework 安全更新和修补程序

这篇文章演示如何找出哪些.NET Framework 安全更新和修补程序安装在计算机上。

> [!NOTE]
> 这篇文章中所示的所有技术都需要具有管理权限的帐户。

## <a name="to-find-installed-updates-using-the-registry"></a>若要查找已安装的更新使用注册表

在 Windows 注册表中列出的已安装的安全更新和每个版本的.NET Framework 的计算机上安装的修补程序。 你可以使用注册表编辑器 (*regedit.exe*) 程序，可以查看此信息。

1. 打开程序 **regedit.exe**。 在 Windows 8 和更高版本中，右键单击**启动** ![Windows 徽标](../get-started/media/windowskeyboardlogo.png "Windowskeyboardlogo")，然后选择**运行**。 在**打开**框中，输入**regedit**和选择**确定**。

2. 在注册表编辑器中，打开以下子项：

     `HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\Updates`

     已安装的更新在标识适用的 .NET Framework 版本的子项下方列出。 每个更新均由知识库 (KB) 编号进行标识。

在注册表编辑器中，.NET Framework 版本和每个版本已安装的更新都保存在不同的子项中。 有关检测安装的版本号的信息，请参阅[如何： 确定安装了哪些.NET Framework 版本](../../../docs/framework/migration-guide/how-to-determine-which-versions-are-installed.md)。

## <a name="to-find-installed-updates-by-querying-the-registry-in-code"></a>若要查找已安装的更新通过在代码中查询注册表

下面的示例以编程方式确定的.NET Framework 安全更新和的计算机安装的修补程序：

[!code-csharp[ListUpdates](../../../samples/snippets/csharp/VS_Snippets_CLR/listupdates/cs/program.cs)]
[!code-vb[ListUpdates](../../../samples/snippets/visualbasic/VS_Snippets_CLR/listupdates/vb/program.vb)]

该示例生成类似于以下输出：

```console
Microsoft .NET Framework 4 Client Profile
  KB2468871
  KB2468871v2
  KB2478063
  KB2533523
  KB2544514
  KB2600211
  KB2600217
Microsoft .NET Framework 4 Extended
  KB2468871
  KB2468871v2
  KB2478063
  KB2533523
  KB2544514
  KB2600211
  KB2600217
```

## <a name="to-find-installed-updates-by-querying-the-registry-in-powershell"></a>若要查找已安装的更新通过在 PowerShell 中查询注册表

下面的示例演示如何确定.NET Framework 安全更新和使用 PowerShell 的计算机安装的修补程序：

```powershell
 Get-ChildItem "HKLM:SOFTWARE\Wow6432Node\Microsoft\Updates\*" -Recurse | Where-Object {$_.name -like
 "*.NET Framework*"}
```

该示例生成类似于以下输出：

```console
    Hive: HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\Updates\Microsoft .NET Framework 4 Client Profile


Name                           Property
----                           --------
KB2468871                      ThisVersionInstalled : Y
KB2468871v2                    ThisVersionInstalled : Y
KB2478063                      ThisVersionInstalled : Y
KB2533523                      ThisVersionInstalled : Y
KB2544514                      ThisVersionInstalled : Y
KB2600211                      ThisVersionInstalled : Y
KB2600217                      ThisVersionInstalled : Y


    Hive: HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\Updates\Microsoft .NET Framework 4 Extended


Name                           Property
----                           --------
KB2468871                      ThisVersionInstalled : Y
KB2468871v2                    ThisVersionInstalled : Y
KB2478063                      ThisVersionInstalled : Y
KB2533523                      ThisVersionInstalled : Y
KB2544514                      ThisVersionInstalled : Y
KB2600211                      ThisVersionInstalled : Y
KB2600217                      ThisVersionInstalled : Y
```

## <a name="see-also"></a>请参阅

[如何： 确定安装了哪些.NET Framework 版本](../../../docs/framework/migration-guide/how-to-determine-which-versions-are-installed.md)  
[安装.NET Framework 为开发人员](../../../docs/framework/install/guide-for-developers.md)  
[版本和依赖关系](../../../docs/framework/migration-guide/versions-and-dependencies.md)
