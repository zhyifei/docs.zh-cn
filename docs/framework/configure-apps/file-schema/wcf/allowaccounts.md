---
title: <allowAccounts>
ms.date: 03/30/2017
ms.assetid: 166923a9-a8ac-478f-92f9-529d9667f3a6
ms.openlocfilehash: c62f29c53d807cab397ff09c6163d924a71ea319
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69926601"
---
# <a name="allowaccounts"></a><span data-ttu-id="e3467-101">\<allowAccounts></span><span class="sxs-lookup"><span data-stu-id="e3467-101">\<allowAccounts></span></span>
<span data-ttu-id="e3467-102">包含一个配置元素集合, 这些元素为承载 Windows Communication Foundation (WCF) 服务且被授予对共享服务的连接访问权限的进程指定用户帐户。</span><span class="sxs-lookup"><span data-stu-id="e3467-102">Contains a collection of configuration elements that specify user accounts for processes that host Windows Communication Foundation (WCF) services, and are granted connection access to the sharing service.</span></span>  
  
 <span data-ttu-id="e3467-103">\<system.serviceModel.activation></span><span class="sxs-lookup"><span data-stu-id="e3467-103">\<system.serviceModel.activation></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e3467-104">语法</span><span class="sxs-lookup"><span data-stu-id="e3467-104">Syntax</span></span>  
  
```xml  
<allowAccounts>
  <add securityIdentifier="String" />
</allowAccounts>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e3467-105">特性和元素</span><span class="sxs-lookup"><span data-stu-id="e3467-105">Attributes and Elements</span></span>  
 <span data-ttu-id="e3467-106">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="e3467-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e3467-107">特性</span><span class="sxs-lookup"><span data-stu-id="e3467-107">Attributes</span></span>  
 <span data-ttu-id="e3467-108">无。</span><span class="sxs-lookup"><span data-stu-id="e3467-108">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="e3467-109">子元素</span><span class="sxs-lookup"><span data-stu-id="e3467-109">Child Elements</span></span>  
  
|<span data-ttu-id="e3467-110">特性</span><span class="sxs-lookup"><span data-stu-id="e3467-110">Attribute</span></span>|<span data-ttu-id="e3467-111">描述</span><span class="sxs-lookup"><span data-stu-id="e3467-111">Description</span></span>|  
|---------------|-----------------|  
|[<span data-ttu-id="e3467-112">\<add></span><span class="sxs-lookup"><span data-stu-id="e3467-112">\<add></span></span>](add-of-allowaccounts.md)|<span data-ttu-id="e3467-113">为承载 WCF 服务且被授予对共享服务的连接访问权限的进程添加用户帐户</span><span class="sxs-lookup"><span data-stu-id="e3467-113">Adds a user account for processes that host WCF services, and are granted connection access to the sharing service</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="e3467-114">父元素</span><span class="sxs-lookup"><span data-stu-id="e3467-114">Parent Elements</span></span>  
  
|<span data-ttu-id="e3467-115">元素</span><span class="sxs-lookup"><span data-stu-id="e3467-115">Element</span></span>|<span data-ttu-id="e3467-116">描述</span><span class="sxs-lookup"><span data-stu-id="e3467-116">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="e3467-117">[\<net.pipe>](net-pipe.md) or [\<net.tcp>](net-tcp.md)</span><span class="sxs-lookup"><span data-stu-id="e3467-117">[\<net.pipe>](net-pipe.md) or [\<net.tcp>](net-tcp.md)</span></span>|<span data-ttu-id="e3467-118">指定 Net Pipe 或 TCP 共享服务的配置设置。</span><span class="sxs-lookup"><span data-stu-id="e3467-118">Specifies configuration settings for the Net Pipe or TCP sharing services.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e3467-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="e3467-119">See also</span></span>

- <xref:System.ServiceModel.Activation.Configuration.NetTcpSection.AllowAccounts%2A>
- <xref:System.ServiceModel.Activation.Configuration.NetPipeSection.AllowAccounts%2A>
- <xref:System.ServiceModel.Activation.Configuration.SecurityIdentifierElementCollection>
- <xref:System.ServiceModel.Activation.Configuration.SecurityIdentifierElement>
