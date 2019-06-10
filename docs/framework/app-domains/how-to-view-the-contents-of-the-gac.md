---
title: 如何：查看全局程序集缓存的内容
ms.date: 03/30/2017
helpviewer_keywords:
- assemblies [.NET Framework], global assembly cache
- global assembly cache, viewing contents
- viewing assemblies in global assembly cache
- Gacutil.exe
- strong-named assemblies, global assembly cache
- GAC (global assembly cache), viewing contents
- list of assemblies in global assembly cache
- Global Assembly Cache tool
ms.assetid: c5f786a0-969b-4f14-9f02-e77c3384d9af
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c319c5f7c9bb808b2ce7ee10178722287e456339
ms.sourcegitcommit: 155012a8a826ee8ab6aa49b1b3a3b532e7b7d9bd
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/04/2019
ms.locfileid: "66486424"
---
# <a name="how-to-view-the-contents-of-the-global-assembly-cache"></a><span data-ttu-id="0a69b-102">如何：查看全局程序集缓存的内容</span><span class="sxs-lookup"><span data-stu-id="0a69b-102">How to: View the contents of the global assembly cache</span></span>

<span data-ttu-id="0a69b-103">使用[全局程序集缓存工具 (Gacutil.exe)](../tools/gacutil-exe-gac-tool.md) 可查看全局程序集缓存 (GAC) 的内容。</span><span class="sxs-lookup"><span data-stu-id="0a69b-103">Use the [global assembly cache tool (gacutil.exe)](../tools/gacutil-exe-gac-tool.md) to view the contents of the global assembly cache (GAC).</span></span>

## <a name="view-the-assemblies-in-the-gac"></a><span data-ttu-id="0a69b-104">查看 GAC 中的程序集</span><span class="sxs-lookup"><span data-stu-id="0a69b-104">View the assemblies in the GAC</span></span>

<span data-ttu-id="0a69b-105">要查看全局程序集缓存中的程序集列表，请打开 [Visual Studio 适用的开发人员命令提示](../tools/developer-command-prompt-for-vs.md)，然后输入以下命令：</span><span class="sxs-lookup"><span data-stu-id="0a69b-105">To view a list of the assemblies in the global assembly cache, open [Developer Command Prompt for Visual Studio](../tools/developer-command-prompt-for-vs.md), and then enter the following command:</span></span>

```shell
gacutil -l
```

<span data-ttu-id="0a69b-106">或</span><span class="sxs-lookup"><span data-stu-id="0a69b-106">-or-</span></span>

```shell
gacutil /l
```

> [!NOTE]
> <span data-ttu-id="0a69b-107">在 .NET Framework 的早期版本中，可通过 [Shfusion.dll](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/34149zk3(v=vs.100)) Windows shell 扩展在文件资源管理器中查看全局程序集缓存。</span><span class="sxs-lookup"><span data-stu-id="0a69b-107">In earlier versions of the .NET Framework, the [Shfusion.dll](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/34149zk3(v=vs.100)) Windows shell extension enabled you to view the global assembly cache in File Explorer.</span></span> <span data-ttu-id="0a69b-108">从 .NET Framework 4 开始，Shfusion.dll 已淘汰。</span><span class="sxs-lookup"><span data-stu-id="0a69b-108">Beginning with the .NET Framework 4, Shfusion.dll is obsolete.</span></span>

## <a name="see-also"></a><span data-ttu-id="0a69b-109">请参阅</span><span class="sxs-lookup"><span data-stu-id="0a69b-109">See also</span></span>

- [<span data-ttu-id="0a69b-110">使用程序集和全局程序集缓存</span><span class="sxs-lookup"><span data-stu-id="0a69b-110">Working with Assemblies and the Global Assembly Cache</span></span>](working-with-assemblies-and-the-gac.md)
- [<span data-ttu-id="0a69b-111">Gacutil.exe（全局程序集缓存工具）</span><span class="sxs-lookup"><span data-stu-id="0a69b-111">Gacutil.exe (Global Assembly Cache Tool)</span></span>](../tools/gacutil-exe-gac-tool.md)
