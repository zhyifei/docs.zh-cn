---
title: "缓解：长路径支持"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-bcl
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3cbe2d77-6e2c-4665-a6c5-7000b9ad6890
caps.latest.revision: 5
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 138e96c3d45b79ccf30f6a3d39f0af26a48c0117
ms.contentlocale: zh-cn
ms.lasthandoff: 07/28/2017

---
# <a name="mitigation-long-path-support"></a><span data-ttu-id="844bf-102">缓解：长路径支持</span><span class="sxs-lookup"><span data-stu-id="844bf-102">Mitigation: Long Path Support</span></span>
<span data-ttu-id="844bf-103">自定位 [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] 的应用程序起，当路径或完全限定的文件名超过 260（或 `MAX_PATH`）个字符时，文件系统 I/O 方法不再自动引发 <xref:System.IO.PathTooLongException>。</span><span class="sxs-lookup"><span data-stu-id="844bf-103">Starting with apps that target the [!INCLUDE[net_v462](../../../includes/net-v462-md.md)],  file system I/O methods not longer automatically throw a <xref:System.IO.PathTooLongException> if a path or fully qualified file name exceeds 260 (or `MAX_PATH`) characters.</span></span> <span data-ttu-id="844bf-104">相反，支持最多包含 32000 个字符的长路径。</span><span class="sxs-lookup"><span data-stu-id="844bf-104">Instead, long paths of up to 32K characters are supported.</span></span>  
  
## <a name="impact"></a><span data-ttu-id="844bf-105">影响</span><span class="sxs-lookup"><span data-stu-id="844bf-105">Impact</span></span>  
 <span data-ttu-id="844bf-106">以前在路径超过 260 个字符时自动引发 <xref:System.IO.PathTooLongException> 的应用程序在重新编译为定位 [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] 后，现仅在下列情况下引发 <xref:System.IO.PathTooLongException>：</span><span class="sxs-lookup"><span data-stu-id="844bf-106">Apps recompiled to target the [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] and that previously threw a <xref:System.IO.PathTooLongException> automatically because a path exceeded 260 characters will now throw a <xref:System.IO.PathTooLongException> only under the following conditions:</span></span>  
  
-   <span data-ttu-id="844bf-107">路径长度必须大于 <xref:System.Int16.MaxValue?displayProperty=fullName> (32,767) 个字符。</span><span class="sxs-lookup"><span data-stu-id="844bf-107">The length of the path is greater than  <xref:System.Int16.MaxValue?displayProperty=fullName> (32,767) characters.</span></span>  
  
-   <span data-ttu-id="844bf-108">操作系统返回 `COR_E_PATHTOOLONG` 或其等同项。</span><span class="sxs-lookup"><span data-stu-id="844bf-108">The operating system returns `COR_E_PATHTOOLONG` or its equivalent.</span></span>  
  
 <span data-ttu-id="844bf-109">定位 [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] 及更低版本应用的旧行为是，只要路径超出 260 个字符，运行时就会自动引发 <xref:System.IO.PathTooLongException>。</span><span class="sxs-lookup"><span data-stu-id="844bf-109">The legacy behavior for apps that target the[!INCLUDE[net_v461](../../../includes/net-v461-md.md)] and earlier is that the runtime automatically throws a <xref:System.IO.PathTooLongException> whenever a path exceeds 260 characters.</span></span>  
  
## <a name="mitigation"></a><span data-ttu-id="844bf-110">缓解操作</span><span class="sxs-lookup"><span data-stu-id="844bf-110">Mitigation</span></span>  
 <span data-ttu-id="844bf-111">对于定位 [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] 的应用程序，如果不需要此支持，可以在 app.config 文件的 [\<runtime>](../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md) 部分中添加以下内容，从而选择禁用长路径：</span><span class="sxs-lookup"><span data-stu-id="844bf-111">For apps that target the [!INCLUDE[net_v462](../../../includes/net-v462-md.md)], you can opt out of long path support if it is not desirable by adding the following to    to the [\<runtime>](../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md) section of your app.config file:</span></span>  
  
```xml  
<runtime>   
   <AppContextSwitchOverrides value="Switch.System.IO.BlockLongPaths=true" />   
</runtime>  
```  
  
 <span data-ttu-id="844bf-112">对于定位旧版 .NET Framework，但在 [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] 或更高版本上运行的应用程序，可以在 app.config 文件的 [\<runtime>](../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md) 部分中添加以下内容，从而选择启用长路径：</span><span class="sxs-lookup"><span data-stu-id="844bf-112">For apps that target earlier versions of the .NET Framework but run on the [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] or later., you can opt in to long path support by adding the following to    to the [\<runtime>](../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md) section of your app.config file:</span></span>  
  
```xml  
<runtime>   
   <AppContextSwitchOverrides value="Switch.System.IO.BlockLongPaths=false" />   
</runtime>  
```  
  
## <a name="see-also"></a><span data-ttu-id="844bf-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="844bf-113">See Also</span></span>  
 [<span data-ttu-id="844bf-114">重定目标更改</span><span class="sxs-lookup"><span data-stu-id="844bf-114">Retargeting Changes</span></span>](../../../docs/framework/migration-guide/retargeting-changes-in-the-net-framework-4-6-2.md)

