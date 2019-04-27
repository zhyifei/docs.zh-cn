---
title: <allowAccounts>
ms.date: 03/30/2017
ms.assetid: 166923a9-a8ac-478f-92f9-529d9667f3a6
ms.openlocfilehash: f9def3004b116afdc629de136cdfe0b0eb6e75c2
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61673532"
---
# <a name="allowaccounts"></a><span data-ttu-id="07243-101">\<allowAccounts></span><span class="sxs-lookup"><span data-stu-id="07243-101">\<allowAccounts></span></span>
<span data-ttu-id="07243-102">包含指定用户帐户对进程承载 Windows Communication Foundation (WCF) 服务并被授予了对该共享服务的连接访问的配置元素的集合。</span><span class="sxs-lookup"><span data-stu-id="07243-102">Contains a collection of configuration elements that specify user accounts for processes that host Windows Communication Foundation (WCF) services, and are granted connection access to the sharing service.</span></span>  
  
 <span data-ttu-id="07243-103">\<system.serviceModel.activation></span><span class="sxs-lookup"><span data-stu-id="07243-103">\<system.serviceModel.activation></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="07243-104">语法</span><span class="sxs-lookup"><span data-stu-id="07243-104">Syntax</span></span>  
  
```xml  
<allowAccounts>
  <add securityIdentifier="String" />
</allowAccounts>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="07243-105">特性和元素</span><span class="sxs-lookup"><span data-stu-id="07243-105">Attributes and Elements</span></span>  
 <span data-ttu-id="07243-106">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="07243-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="07243-107">特性</span><span class="sxs-lookup"><span data-stu-id="07243-107">Attributes</span></span>  
 <span data-ttu-id="07243-108">无。</span><span class="sxs-lookup"><span data-stu-id="07243-108">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="07243-109">子元素</span><span class="sxs-lookup"><span data-stu-id="07243-109">Child Elements</span></span>  
  
|<span data-ttu-id="07243-110">特性</span><span class="sxs-lookup"><span data-stu-id="07243-110">Attribute</span></span>|<span data-ttu-id="07243-111">描述</span><span class="sxs-lookup"><span data-stu-id="07243-111">Description</span></span>|  
|---------------|-----------------|  
|[<span data-ttu-id="07243-112">\<add></span><span class="sxs-lookup"><span data-stu-id="07243-112">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-allowaccounts.md)|<span data-ttu-id="07243-113">添加进程的承载 WCF 服务并被授予对共享服务的连接访问权限的用户的帐户</span><span class="sxs-lookup"><span data-stu-id="07243-113">Adds a user account for processes that host WCF services, and are granted connection access to the sharing service</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="07243-114">父元素</span><span class="sxs-lookup"><span data-stu-id="07243-114">Parent Elements</span></span>  
  
|<span data-ttu-id="07243-115">元素</span><span class="sxs-lookup"><span data-stu-id="07243-115">Element</span></span>|<span data-ttu-id="07243-116">描述</span><span class="sxs-lookup"><span data-stu-id="07243-116">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="07243-117">[\<net.pipe>](../../../../../docs/framework/configure-apps/file-schema/wcf/net-pipe.md) or [\<net.tcp>](../../../../../docs/framework/configure-apps/file-schema/wcf/net-tcp.md)</span><span class="sxs-lookup"><span data-stu-id="07243-117">[\<net.pipe>](../../../../../docs/framework/configure-apps/file-schema/wcf/net-pipe.md) or [\<net.tcp>](../../../../../docs/framework/configure-apps/file-schema/wcf/net-tcp.md)</span></span>|<span data-ttu-id="07243-118">指定 Net Pipe 或 TCP 共享服务的配置设置。</span><span class="sxs-lookup"><span data-stu-id="07243-118">Specifies configuration settings for the Net Pipe or TCP sharing services.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="07243-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="07243-119">See also</span></span>

- <xref:System.ServiceModel.Activation.Configuration.NetTcpSection.AllowAccounts%2A>
- <xref:System.ServiceModel.Activation.Configuration.NetPipeSection.AllowAccounts%2A>
- <xref:System.ServiceModel.Activation.Configuration.SecurityIdentifierElementCollection>
- <xref:System.ServiceModel.Activation.Configuration.SecurityIdentifierElement>
