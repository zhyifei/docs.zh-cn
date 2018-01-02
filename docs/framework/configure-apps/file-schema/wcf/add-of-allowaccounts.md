---
title: "&lt;allowAccounts&gt; 的 &lt;add&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 763c7b1f-e7b0-4d99-a42c-4506fcb8da00
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 064c9d438832142e1f761d0d33db528dbe73ef2a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="ltaddgt-of-ltallowaccountsgt"></a><span data-ttu-id="b285f-102">&lt;allowAccounts&gt; 的 &lt;add&gt;</span><span class="sxs-lookup"><span data-stu-id="b285f-102">&lt;add&gt; of &lt;allowAccounts&gt;</span></span>
<span data-ttu-id="b285f-103">指定进程的用户帐户，这些进程承载 [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] 服务并被授予了对共享服务的连接访问权限。</span><span class="sxs-lookup"><span data-stu-id="b285f-103">Specifies a user account for processes that host [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] services, and are granted connection access to the sharing service.</span></span>  
  
 <span data-ttu-id="b285f-104">\<system.serviceModel.activation ></span><span class="sxs-lookup"><span data-stu-id="b285f-104">\<system.serviceModel.activation></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b285f-105">语法</span><span class="sxs-lookup"><span data-stu-id="b285f-105">Syntax</span></span>  
  
```xml  
<allowAccounts>  
   <add securityIdentifier="String"/>  
</allowAccounts>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b285f-106">特性和元素</span><span class="sxs-lookup"><span data-stu-id="b285f-106">Attributes and Elements</span></span>  
 <span data-ttu-id="b285f-107">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="b285f-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b285f-108">特性</span><span class="sxs-lookup"><span data-stu-id="b285f-108">Attributes</span></span>  
  
|<span data-ttu-id="b285f-109">特性</span><span class="sxs-lookup"><span data-stu-id="b285f-109">Attribute</span></span>|<span data-ttu-id="b285f-110">描述</span><span class="sxs-lookup"><span data-stu-id="b285f-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="b285f-111">securityIdentifier</span><span class="sxs-lookup"><span data-stu-id="b285f-111">securityIdentifier</span></span>|<span data-ttu-id="b285f-112">一个字符串，指定用于标识用户帐户的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="b285f-112">A string that specifies a unique identifier used to identify a user account.</span></span> <span data-ttu-id="b285f-113">默认值为 LocalSystem、Administrators、NS、LS 和 IIS_USRS。</span><span class="sxs-lookup"><span data-stu-id="b285f-113">The default values are LocalSystem, Administrators, NS, LS, and IIS_USRS.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b285f-114">子元素</span><span class="sxs-lookup"><span data-stu-id="b285f-114">Child Elements</span></span>  
 <span data-ttu-id="b285f-115">无。</span><span class="sxs-lookup"><span data-stu-id="b285f-115">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="b285f-116">父元素</span><span class="sxs-lookup"><span data-stu-id="b285f-116">Parent Elements</span></span>  
  
|<span data-ttu-id="b285f-117">元素</span><span class="sxs-lookup"><span data-stu-id="b285f-117">Element</span></span>|<span data-ttu-id="b285f-118">描述</span><span class="sxs-lookup"><span data-stu-id="b285f-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b285f-119">\<allowAccounts ></span><span class="sxs-lookup"><span data-stu-id="b285f-119">\<allowAccounts></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/allowaccounts.md)|<span data-ttu-id="b285f-120">一个配置元素集合，这些元素所包含的 `securityIdentifier` 属性用于指定进程的用户帐户，这些进程承载 [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] 服务并被授予了对该共享服务的连接访问权限。</span><span class="sxs-lookup"><span data-stu-id="b285f-120">A collection of configuration elements that contain a `securityIdentifier` attribute to specify user accounts for processes that host [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] services, and are granted connection access to the sharing service.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="b285f-121">示例</span><span class="sxs-lookup"><span data-stu-id="b285f-121">Example</span></span>  
 <span data-ttu-id="b285f-122">下面的配置示例将用户帐户的五个默认标识符添加到此集合中。</span><span class="sxs-lookup"><span data-stu-id="b285f-122">The following configuration example adds the five default identifiers for user accounts to this collection.</span></span>  
  
```xml  
<allowAccounts>  
   // LocalSystem account  
   <add securityIdentifier="S-1-5-18"/>  
   // LocalService account  
   <add securityIdentifier="S-1-5-19"/>  
   // Administrators account  
   <add securityIdentifier="S-1-5-20"/>  
   // Network Service account  
   <add securityIdentifier="S-1-5-32-544" />  
   // IIS_IUSRS account (Vista only)  
   <add securityIdentifier="S-1-5-32-568"/>  
</allowAccounts>  
```  
  
## <a name="see-also"></a><span data-ttu-id="b285f-123">请参阅</span><span class="sxs-lookup"><span data-stu-id="b285f-123">See Also</span></span>  
 <xref:System.ServiceModel.Activation.Configuration.NetTcpSection.AllowAccounts%2A>  
 <xref:System.ServiceModel.Activation.Configuration.NetPipeSection.AllowAccounts%2A>  
 <xref:System.ServiceModel.Activation.Configuration.SecurityIdentifierElementCollection>  
 <xref:System.ServiceModel.Activation.Configuration.SecurityIdentifierElement>
