---
title: <add> 的 <allowAccounts>
ms.date: 03/30/2017
ms.assetid: 763c7b1f-e7b0-4d99-a42c-4506fcb8da00
ms.openlocfilehash: 02654b8ab198a2b161b3044c1f3aa452761a6a4c
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/06/2019
ms.locfileid: "70398381"
---
# <a name="add-of-allowaccounts"></a><span data-ttu-id="cedc6-102">\<添加 allowAccounts > \<的 ></span><span class="sxs-lookup"><span data-stu-id="cedc6-102">\<add> of \<allowAccounts></span></span>
<span data-ttu-id="cedc6-103">为承载 WCF 服务且被授予对共享服务的连接访问权限的进程指定用户帐户。</span><span class="sxs-lookup"><span data-stu-id="cedc6-103">Specifies a user account for processes that host WCF services, and are granted connection access to the sharing service.</span></span>  
  
<span data-ttu-id="cedc6-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="cedc6-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="cedc6-105">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel-activation.md)</span><span class="sxs-lookup"><span data-stu-id="cedc6-105">&nbsp;&nbsp;[**\<system.serviceModel.activation>**](system-servicemodel-activation.md)</span></span>\
<span data-ttu-id="cedc6-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<net.pipe >** ](net-pipe.md)</span><span class="sxs-lookup"><span data-stu-id="cedc6-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<net.pipe>**](net-pipe.md)</span></span>\
<span data-ttu-id="cedc6-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<allowAccounts >** ](allowaccounts.md)</span><span class="sxs-lookup"><span data-stu-id="cedc6-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<allowAccounts>**](allowaccounts.md)</span></span>\
<span data-ttu-id="cedc6-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<添加 >**</span><span class="sxs-lookup"><span data-stu-id="cedc6-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cedc6-109">语法</span><span class="sxs-lookup"><span data-stu-id="cedc6-109">Syntax</span></span>  
  
```xml  
<allowAccounts>
  <add securityIdentifier="String" />
</allowAccounts>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="cedc6-110">特性和元素</span><span class="sxs-lookup"><span data-stu-id="cedc6-110">Attributes and Elements</span></span>  
 <span data-ttu-id="cedc6-111">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="cedc6-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="cedc6-112">特性</span><span class="sxs-lookup"><span data-stu-id="cedc6-112">Attributes</span></span>  
  
|<span data-ttu-id="cedc6-113">特性</span><span class="sxs-lookup"><span data-stu-id="cedc6-113">Attribute</span></span>|<span data-ttu-id="cedc6-114">描述</span><span class="sxs-lookup"><span data-stu-id="cedc6-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="cedc6-115">securityIdentifier</span><span class="sxs-lookup"><span data-stu-id="cedc6-115">securityIdentifier</span></span>|<span data-ttu-id="cedc6-116">一个字符串，指定用于标识用户帐户的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="cedc6-116">A string that specifies a unique identifier used to identify a user account.</span></span> <span data-ttu-id="cedc6-117">默认值为 LocalSystem、Administrators、NS、LS 和 IIS_USRS。</span><span class="sxs-lookup"><span data-stu-id="cedc6-117">The default values are LocalSystem, Administrators, NS, LS, and IIS_USRS.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="cedc6-118">子元素</span><span class="sxs-lookup"><span data-stu-id="cedc6-118">Child Elements</span></span>  
 <span data-ttu-id="cedc6-119">无。</span><span class="sxs-lookup"><span data-stu-id="cedc6-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="cedc6-120">父元素</span><span class="sxs-lookup"><span data-stu-id="cedc6-120">Parent Elements</span></span>  
  
|<span data-ttu-id="cedc6-121">元素</span><span class="sxs-lookup"><span data-stu-id="cedc6-121">Element</span></span>|<span data-ttu-id="cedc6-122">描述</span><span class="sxs-lookup"><span data-stu-id="cedc6-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="cedc6-123">\<allowAccounts></span><span class="sxs-lookup"><span data-stu-id="cedc6-123">\<allowAccounts></span></span>](allowaccounts.md)|<span data-ttu-id="cedc6-124">一个配置元素的集合，这些元素`securityIdentifier`包含一个属性，用于为承载 WCF 服务并被授予对共享服务的连接访问权限的进程指定用户帐户。</span><span class="sxs-lookup"><span data-stu-id="cedc6-124">A collection of configuration elements that contain a `securityIdentifier` attribute to specify user accounts for processes that host WCF services, and are granted connection access to the sharing service.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="cedc6-125">示例</span><span class="sxs-lookup"><span data-stu-id="cedc6-125">Example</span></span>  
 <span data-ttu-id="cedc6-126">下面的配置示例将用户帐户的五个默认标识符添加到此集合中。</span><span class="sxs-lookup"><span data-stu-id="cedc6-126">The following configuration example adds the five default identifiers for user accounts to this collection.</span></span>  
  
```xml  
<allowAccounts>
  <!-- LocalSystem account -->
  <add securityIdentifier="S-1-5-18" />
  <!-- LocalService account -->
  <add securityIdentifier="S-1-5-19" />
  <!-- Administrators account -->
  <add securityIdentifier="S-1-5-20" />
  <!-- Network Service account -->
  <add securityIdentifier="S-1-5-32-544" />
  <!-- IIS_IUSRS account (Vista only) -->
  <add securityIdentifier="S-1-5-32-568" />
</allowAccounts>
```  
  
## <a name="see-also"></a><span data-ttu-id="cedc6-127">请参阅</span><span class="sxs-lookup"><span data-stu-id="cedc6-127">See also</span></span>

- <xref:System.ServiceModel.Activation.Configuration.NetTcpSection.AllowAccounts%2A>
- <xref:System.ServiceModel.Activation.Configuration.NetPipeSection.AllowAccounts%2A>
- <xref:System.ServiceModel.Activation.Configuration.SecurityIdentifierElementCollection>
- <xref:System.ServiceModel.Activation.Configuration.SecurityIdentifierElement>
