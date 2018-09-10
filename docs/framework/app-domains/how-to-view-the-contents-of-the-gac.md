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
ms.openlocfilehash: 3650de934cb3d2940d0e8e971d03aff856bddfd7
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/04/2018
ms.locfileid: "43515474"
---
# <a name="how-to-view-the-contents-of-the-global-assembly-cache"></a><span data-ttu-id="7b8c6-102">如何：查看全局程序集缓存的内容</span><span class="sxs-lookup"><span data-stu-id="7b8c6-102">How to: View the Contents of the Global Assembly Cache</span></span>
<span data-ttu-id="7b8c6-103">使用[全局程序集缓存工具 (Gacutil.exe)](../../../docs/framework/tools/gacutil-exe-gac-tool.md) 可查看全局程序集缓存的内容。</span><span class="sxs-lookup"><span data-stu-id="7b8c6-103">Use the [Global Assembly Cache tool (Gacutil.exe)](../../../docs/framework/tools/gacutil-exe-gac-tool.md) to view the contents of the global assembly cache.</span></span>  
  
### <a name="to-view-a-list-of-the-assemblies-in-the-global-assembly-cache"></a><span data-ttu-id="7b8c6-104">查看全局程序集缓存中的程序集列表</span><span class="sxs-lookup"><span data-stu-id="7b8c6-104">To view a list of the assemblies in the global assembly cache</span></span>  
  
1.  <span data-ttu-id="7b8c6-105">在 [Visual Studio 命令提示符](../../../docs/framework/tools/developer-command-prompt-for-vs.md)处，键入以下命令：</span><span class="sxs-lookup"><span data-stu-id="7b8c6-105">At the [Visual Studio command prompt](../../../docs/framework/tools/developer-command-prompt-for-vs.md), type the following command:</span></span>  
  
     <span data-ttu-id="7b8c6-106">gacutil -l </span><span class="sxs-lookup"><span data-stu-id="7b8c6-106">**gacutil -l** </span></span>  
     <span data-ttu-id="7b8c6-107">或</span><span class="sxs-lookup"><span data-stu-id="7b8c6-107">-or-</span></span>  
    <span data-ttu-id="7b8c6-108">gacutil -l</span><span class="sxs-lookup"><span data-stu-id="7b8c6-108">**gacutil /l**</span></span>  
  
 <span data-ttu-id="7b8c6-109">在 .NET Framework 的早期版本中，可通过 [Shfusion.dll](https://msdn.microsoft.com/library/0d9464cf-ddba-4ca9-bbec-f678fb58f380) Windows shell 扩展在文件资源管理器中查看全局程序集缓存。</span><span class="sxs-lookup"><span data-stu-id="7b8c6-109">In earlier versions of the .NET Framework, the [Shfusion.dll](https://msdn.microsoft.com/library/0d9464cf-ddba-4ca9-bbec-f678fb58f380) Windows shell extension enabled you to view the global assembly cache in File Explorer.</span></span> <span data-ttu-id="7b8c6-110">从 [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)]开始，Shfusion.dll 已过时。</span><span class="sxs-lookup"><span data-stu-id="7b8c6-110">Beginning with the [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)], Shfusion.dll is obsolete.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7b8c6-111">请参阅</span><span class="sxs-lookup"><span data-stu-id="7b8c6-111">See Also</span></span>  
 [<span data-ttu-id="7b8c6-112">使用程序集和全局程序集缓存</span><span class="sxs-lookup"><span data-stu-id="7b8c6-112">Working with Assemblies and the Global Assembly Cache</span></span>](../../../docs/framework/app-domains/working-with-assemblies-and-the-gac.md)  
 [<span data-ttu-id="7b8c6-113">Gacutil.exe（全局程序集缓存工具）</span><span class="sxs-lookup"><span data-stu-id="7b8c6-113">Gacutil.exe (Global Assembly Cache Tool)</span></span>](../../../docs/framework/tools/gacutil-exe-gac-tool.md)
