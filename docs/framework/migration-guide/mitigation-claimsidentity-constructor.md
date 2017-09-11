---
title: "缓解：ClaimsIdentity 构造函数"
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
ms.assetid: 946903f1-0fbf-4f67-805b-1eb48352024d
caps.latest.revision: 5
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: a50cbd69aa1f2c72adc9fc4d10a070f5faa0cf54
ms.contentlocale: zh-cn
ms.lasthandoff: 07/28/2017

---
# <a name="mitigation-claimsidentity-constructor"></a><span data-ttu-id="0605a-102">缓解：ClaimsIdentity 构造函数</span><span class="sxs-lookup"><span data-stu-id="0605a-102">Mitigation: ClaimsIdentity Constructor</span></span>
<span data-ttu-id="0605a-103">自 [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] 起，<xref:System.Security.Claims.ClaimsIdentity.%23ctor%28System.Security.Principal.IIdentity%29?displayProperty=fullName> 构造函数设置 <xref:System.Security.Claims.ClaimsIdentity.Actor%2A?displayProperty=fullName> 属性的方式有所更改。</span><span class="sxs-lookup"><span data-stu-id="0605a-103">Starting with the [!INCLUDE[net_v462](../../../includes/net-v462-md.md)], there is change in how the <xref:System.Security.Claims.ClaimsIdentity.%23ctor%28System.Security.Principal.IIdentity%29?displayProperty=fullName> constructor sets the <xref:System.Security.Claims.ClaimsIdentity.Actor%2A?displayProperty=fullName> property.</span></span> <span data-ttu-id="0605a-104">如果 <xref:System.Security.Principal.IIdentity> 参数是 <xref:System.Security.Claims.ClaimsIdentity> 对象，且该 <xref:System.Security.Claims.ClaimsIdentity> 对象的 <xref:System.Security.Claims.ClaimsIdentity.Actor%2A> 属性不为 `null`，则 <xref:System.Security.Claims.ClaimsIdentity.Actor%2A> 属性是使用 <xref:System.Security.Claims.ClaimsIdentity.Clone%2A?displayProperty=fullName> 方法附加的。</span><span class="sxs-lookup"><span data-stu-id="0605a-104">If the <xref:System.Security.Principal.IIdentity> argument is a <xref:System.Security.Claims.ClaimsIdentity> object, and the <xref:System.Security.Claims.ClaimsIdentity.Actor%2A> property of that <xref:System.Security.Claims.ClaimsIdentity> object is not `null`, the <xref:System.Security.Claims.ClaimsIdentity.Actor%2A> property is attached by using the <xref:System.Security.Claims.ClaimsIdentity.Clone%2A?displayProperty=fullName> method.</span></span> <span data-ttu-id="0605a-105">在 [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] 中，<xref:System.Security.Claims.ClaimsIdentity.Actor%2A> 属性以现有引用的形式附加。</span><span class="sxs-lookup"><span data-stu-id="0605a-105">In the [!INCLUDE[net_v461](../../../includes/net-v461-md.md)], the <xref:System.Security.Claims.ClaimsIdentity.Actor%2A> property is attached as a  existing reference.</span></span>  
  
## <a name="impact"></a><span data-ttu-id="0605a-106">影响</span><span class="sxs-lookup"><span data-stu-id="0605a-106">Impact</span></span>  
 <span data-ttu-id="0605a-107">自 [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] 起，新对象 <xref:System.Security.Claims.ClaimsIdentity> 的 <xref:System.Security.Claims.ClaimsIdentity.Actor%2A?displayProperty=fullName> 属性与构造函数 <xref:System.Security.Principal.IIdentity> 参数的 <xref:System.Security.Claims.ClaimsIdentity.Actor%2A?displayProperty=fullName> 属性不相等。</span><span class="sxs-lookup"><span data-stu-id="0605a-107">Starting with the [!INCLUDE[net_v462](../../../includes/net-v462-md.md)], the <xref:System.Security.Claims.ClaimsIdentity.Actor%2A?displayProperty=fullName> property of the new <xref:System.Security.Claims.ClaimsIdentity> object is not equal to the <xref:System.Security.Claims.ClaimsIdentity.Actor%2A?displayProperty=fullName> property of the constructor's <xref:System.Security.Principal.IIdentity> argument.</span></span> <span data-ttu-id="0605a-108">在 [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] 及更低版本中，属性是相等的。</span><span class="sxs-lookup"><span data-stu-id="0605a-108">In the [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] and earlier versions, it is equal.</span></span>  
  
## <a name="mitigation"></a><span data-ttu-id="0605a-109">缓解操作</span><span class="sxs-lookup"><span data-stu-id="0605a-109">Mitigation</span></span>  
 <span data-ttu-id="0605a-110">如果不需要此行为，可以在应用程序配置文件中将 `Switch.System.Security.ClaimsIdentity.SetActorAsReferenceWhenCopyingClaimsIdentity` 开关设置为 `true`，从而还原旧行为。</span><span class="sxs-lookup"><span data-stu-id="0605a-110">If this behavior is undesirable, you can restore the previous behavior by setting the `Switch.System.Security.ClaimsIdentity.SetActorAsReferenceWhenCopyingClaimsIdentity` switch in your application configuration file to `true`.</span></span> <span data-ttu-id="0605a-111">为此，必须在 web.config 文件的 [\<runtime>](../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md) 部分中添加以下内容：</span><span class="sxs-lookup"><span data-stu-id="0605a-111">This requires that you add the following to  the [\<runtime>](../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md) section of your web.config file:</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <AppContextSwitchOverrides value="Switch.System.Security.ClaimsIdentity.SetActorAsReferenceWhenCopyingClaimsIdentity=true" />  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="0605a-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0605a-112">See Also</span></span>  
 [<span data-ttu-id="0605a-113">重定目标更改</span><span class="sxs-lookup"><span data-stu-id="0605a-113">Retargeting Changes</span></span>](../../../docs/framework/migration-guide/retargeting-changes-in-the-net-framework-4-6.md)

