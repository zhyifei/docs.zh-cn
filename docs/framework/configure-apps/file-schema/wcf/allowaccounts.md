---
title: <allowAccounts>
ms.date: 03/30/2017
ms.assetid: 166923a9-a8ac-478f-92f9-529d9667f3a6
ms.openlocfilehash: 74b9d51b7400469c96fc9c8b36e4b0fb1d46969b
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/06/2019
ms.locfileid: "70398406"
---
# <a name="allowaccounts"></a><span data-ttu-id="2c9dc-101">\<allowAccounts></span><span class="sxs-lookup"><span data-stu-id="2c9dc-101">\<allowAccounts></span></span>
<span data-ttu-id="2c9dc-102">包含一个配置元素集合，这些元素为承载 Windows Communication Foundation （WCF）服务且被授予对共享服务的连接访问权限的进程指定用户帐户。</span><span class="sxs-lookup"><span data-stu-id="2c9dc-102">Contains a collection of configuration elements that specify user accounts for processes that host Windows Communication Foundation (WCF) services, and are granted connection access to the sharing service.</span></span>  
  
<span data-ttu-id="2c9dc-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="2c9dc-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="2c9dc-104">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel-activation.md)</span><span class="sxs-lookup"><span data-stu-id="2c9dc-104">&nbsp;&nbsp;[**\<system.serviceModel.activation>**](system-servicemodel-activation.md)</span></span>\
<span data-ttu-id="2c9dc-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<net.pipe >** ](net-pipe.md)</span><span class="sxs-lookup"><span data-stu-id="2c9dc-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<net.pipe>**](net-pipe.md)</span></span>\
<span data-ttu-id="2c9dc-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<allowAccounts >**</span><span class="sxs-lookup"><span data-stu-id="2c9dc-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<allowAccounts>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2c9dc-107">语法</span><span class="sxs-lookup"><span data-stu-id="2c9dc-107">Syntax</span></span>  
  
```xml  
<allowAccounts>
  <add securityIdentifier="String" />
</allowAccounts>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2c9dc-108">特性和元素</span><span class="sxs-lookup"><span data-stu-id="2c9dc-108">Attributes and Elements</span></span>  
 <span data-ttu-id="2c9dc-109">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="2c9dc-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2c9dc-110">特性</span><span class="sxs-lookup"><span data-stu-id="2c9dc-110">Attributes</span></span>  
 <span data-ttu-id="2c9dc-111">无。</span><span class="sxs-lookup"><span data-stu-id="2c9dc-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="2c9dc-112">子元素</span><span class="sxs-lookup"><span data-stu-id="2c9dc-112">Child Elements</span></span>  
  
|<span data-ttu-id="2c9dc-113">特性</span><span class="sxs-lookup"><span data-stu-id="2c9dc-113">Attribute</span></span>|<span data-ttu-id="2c9dc-114">描述</span><span class="sxs-lookup"><span data-stu-id="2c9dc-114">Description</span></span>|  
|---------------|-----------------|  
|[<span data-ttu-id="2c9dc-115">\<add></span><span class="sxs-lookup"><span data-stu-id="2c9dc-115">\<add></span></span>](add-of-allowaccounts.md)|<span data-ttu-id="2c9dc-116">为承载 WCF 服务且被授予对共享服务的连接访问权限的进程添加用户帐户</span><span class="sxs-lookup"><span data-stu-id="2c9dc-116">Adds a user account for processes that host WCF services, and are granted connection access to the sharing service</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="2c9dc-117">父元素</span><span class="sxs-lookup"><span data-stu-id="2c9dc-117">Parent Elements</span></span>  
  
|<span data-ttu-id="2c9dc-118">元素</span><span class="sxs-lookup"><span data-stu-id="2c9dc-118">Element</span></span>|<span data-ttu-id="2c9dc-119">描述</span><span class="sxs-lookup"><span data-stu-id="2c9dc-119">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="2c9dc-120">[\<net.pipe>](net-pipe.md) or [\<net.tcp>](net-tcp.md)</span><span class="sxs-lookup"><span data-stu-id="2c9dc-120">[\<net.pipe>](net-pipe.md) or [\<net.tcp>](net-tcp.md)</span></span>|<span data-ttu-id="2c9dc-121">指定 Net Pipe 或 TCP 共享服务的配置设置。</span><span class="sxs-lookup"><span data-stu-id="2c9dc-121">Specifies configuration settings for the Net Pipe or TCP sharing services.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="2c9dc-122">请参阅</span><span class="sxs-lookup"><span data-stu-id="2c9dc-122">See also</span></span>

- <xref:System.ServiceModel.Activation.Configuration.NetTcpSection.AllowAccounts%2A>
- <xref:System.ServiceModel.Activation.Configuration.NetPipeSection.AllowAccounts%2A>
- <xref:System.ServiceModel.Activation.Configuration.SecurityIdentifierElementCollection>
- <xref:System.ServiceModel.Activation.Configuration.SecurityIdentifierElement>
