---
title: "缓解：路径冒号检查"
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
ms.assetid: a0bb52de-d279-419d-8f23-4b12d1a3f36e
caps.latest.revision: 5
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 8eb6864213aa4420f7a4373b9abbf173880f035f
ms.contentlocale: zh-cn
ms.lasthandoff: 07/28/2017

---
# <a name="mitigation-path-colon-checks"></a><span data-ttu-id="4fe36-102">缓解：路径冒号检查</span><span class="sxs-lookup"><span data-stu-id="4fe36-102">Mitigation: Path Colon Checks</span></span>
<span data-ttu-id="4fe36-103">自定位 [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] 的应用程序起，为了支持以前不受支持的路径，执行了大量更改（无论是在长度方面还是在格式方面）。</span><span class="sxs-lookup"><span data-stu-id="4fe36-103">Starting with apps that target the [!INCLUDE[net_v462](../../../includes/net-v462-md.md)], a number of changes were made to support previously unsupported paths (both in terms of length and format).</span></span> <span data-ttu-id="4fe36-104">特别是，能够更加准确地检查驱动器分隔符语法（冒号）的用法是否正确。</span><span class="sxs-lookup"><span data-stu-id="4fe36-104">In particular, checks for the proper drive separator syntax (the colon) were made more correct.</span></span>  
  
## <a name="impact"></a><span data-ttu-id="4fe36-105">影响</span><span class="sxs-lookup"><span data-stu-id="4fe36-105">Impact</span></span>  
 <span data-ttu-id="4fe36-106">这些更改阻止了 <xref:System.IO.Path.GetDirectoryName%2A?displayProperty=fullName> 和 <xref:System.IO.Path.GetPathRoot%2A?displayProperty=fullName> 方法以前支持的一些 URI 路径。</span><span class="sxs-lookup"><span data-stu-id="4fe36-106">These changes block some URI paths the <xref:System.IO.Path.GetDirectoryName%2A?displayProperty=fullName> and <xref:System.IO.Path.GetPathRoot%2A?displayProperty=fullName> methods previously supported.</span></span>  
  
## <a name="mitigation"></a><span data-ttu-id="4fe36-107">缓解操作</span><span class="sxs-lookup"><span data-stu-id="4fe36-107">Mitigation</span></span>  
 <span data-ttu-id="4fe36-108">若要解决 <xref:System.IO.Path.GetDirectoryName%2A?displayProperty=fullName> 和 <xref:System.IO.Path.GetPathRoot%2A?displayProperty=fullName> 方法不再支持以前可接受的路径的问题，可执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="4fe36-108">To work around the problem of a previously acceptable path that is no longer supported by the <xref:System.IO.Path.GetDirectoryName%2A?displayProperty=fullName> and <xref:System.IO.Path.GetPathRoot%2A?displayProperty=fullName> methods, you can do the following:</span></span>  
  
-   <span data-ttu-id="4fe36-109">从 URL 中手动删除协议。</span><span class="sxs-lookup"><span data-stu-id="4fe36-109">Manually remove the scheme from a URL.</span></span> <span data-ttu-id="4fe36-110">例如，从 URL 中删除 `file://`。</span><span class="sxs-lookup"><span data-stu-id="4fe36-110">For example, remove `file://` from a URL.</span></span>  
  
-   <span data-ttu-id="4fe36-111">将 URI 传递给 <xref:System.Uri> 构造函数，并检索 <xref:System.Uri.LocalPath%2A?displayProperty=fullName> 属性的值。</span><span class="sxs-lookup"><span data-stu-id="4fe36-111">Pass the URI to a <xref:System.Uri> constructor,  and retrieve the value of the <xref:System.Uri.LocalPath%2A?displayProperty=fullName> property.</span></span>  
  
-   <span data-ttu-id="4fe36-112">通过将 `Switch.System.IO.UseLegacyPathHandling`<xref:System.AppContext> 开关设置为 `true` 来选择禁用新的路径规范化。</span><span class="sxs-lookup"><span data-stu-id="4fe36-112">Opt out of the new path normalization by setting the `Switch.System.IO.UseLegacyPathHandling`<xref:System.AppContext> switch to `true`.</span></span>  
  
    ```xml  
    <runtime>  
        <AppContextSwitchOverrides value="Switch.System.IO.UseLegacyPathHandling=true" />    
    </runtime>  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="4fe36-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4fe36-113">See Also</span></span>  
 [<span data-ttu-id="4fe36-114">重定目标更改</span><span class="sxs-lookup"><span data-stu-id="4fe36-114">Retargeting Changes</span></span>](../../../docs/framework/migration-guide/retargeting-changes-in-the-net-framework-4-6-2.md)

