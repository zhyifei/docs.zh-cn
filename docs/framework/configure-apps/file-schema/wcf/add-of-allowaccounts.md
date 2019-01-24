---
title: '&lt;allowAccounts&gt; 的 &lt;add&gt;'
ms.date: 03/30/2017
ms.assetid: 763c7b1f-e7b0-4d99-a42c-4506fcb8da00
ms.openlocfilehash: 63f8e678b81838a25664180888e9e7a8eabd043d
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54721902"
---
# <a name="ltaddgt-of-ltallowaccountsgt"></a><span data-ttu-id="a195c-102">&lt;allowAccounts&gt; 的 &lt;add&gt;</span><span class="sxs-lookup"><span data-stu-id="a195c-102">&lt;add&gt; of &lt;allowAccounts&gt;</span></span>
<span data-ttu-id="a195c-103">指定进程的承载 WCF 服务并被授予对共享服务的连接访问权限的用户的帐户。</span><span class="sxs-lookup"><span data-stu-id="a195c-103">Specifies a user account for processes that host WCF services, and are granted connection access to the sharing service.</span></span>  
  
 <span data-ttu-id="a195c-104">\<system.serviceModel.activation></span><span class="sxs-lookup"><span data-stu-id="a195c-104">\<system.serviceModel.activation></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a195c-105">语法</span><span class="sxs-lookup"><span data-stu-id="a195c-105">Syntax</span></span>  
  
```xml  
<allowAccounts>
  <add securityIdentifier="String" />
</allowAccounts>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a195c-106">特性和元素</span><span class="sxs-lookup"><span data-stu-id="a195c-106">Attributes and Elements</span></span>  
 <span data-ttu-id="a195c-107">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="a195c-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a195c-108">特性</span><span class="sxs-lookup"><span data-stu-id="a195c-108">Attributes</span></span>  
  
|<span data-ttu-id="a195c-109">特性</span><span class="sxs-lookup"><span data-stu-id="a195c-109">Attribute</span></span>|<span data-ttu-id="a195c-110">描述</span><span class="sxs-lookup"><span data-stu-id="a195c-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="a195c-111">securityIdentifier</span><span class="sxs-lookup"><span data-stu-id="a195c-111">securityIdentifier</span></span>|<span data-ttu-id="a195c-112">一个字符串，指定用于标识用户帐户的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="a195c-112">A string that specifies a unique identifier used to identify a user account.</span></span> <span data-ttu-id="a195c-113">默认值为 LocalSystem、Administrators、NS、LS 和 IIS_USRS。</span><span class="sxs-lookup"><span data-stu-id="a195c-113">The default values are LocalSystem, Administrators, NS, LS, and IIS_USRS.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a195c-114">子元素</span><span class="sxs-lookup"><span data-stu-id="a195c-114">Child Elements</span></span>  
 <span data-ttu-id="a195c-115">无。</span><span class="sxs-lookup"><span data-stu-id="a195c-115">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="a195c-116">父元素</span><span class="sxs-lookup"><span data-stu-id="a195c-116">Parent Elements</span></span>  
  
|<span data-ttu-id="a195c-117">元素</span><span class="sxs-lookup"><span data-stu-id="a195c-117">Element</span></span>|<span data-ttu-id="a195c-118">描述</span><span class="sxs-lookup"><span data-stu-id="a195c-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a195c-119">\<allowAccounts></span><span class="sxs-lookup"><span data-stu-id="a195c-119">\<allowAccounts></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/allowaccounts.md)|<span data-ttu-id="a195c-120">包含的配置元素的集合`securityIdentifier`属性指定的进程的承载 WCF 服务并被授予对共享服务的连接访问权限的用户帐户。</span><span class="sxs-lookup"><span data-stu-id="a195c-120">A collection of configuration elements that contain a `securityIdentifier` attribute to specify user accounts for processes that host WCF services, and are granted connection access to the sharing service.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="a195c-121">示例</span><span class="sxs-lookup"><span data-stu-id="a195c-121">Example</span></span>  
 <span data-ttu-id="a195c-122">下面的配置示例将用户帐户的五个默认标识符添加到此集合中。</span><span class="sxs-lookup"><span data-stu-id="a195c-122">The following configuration example adds the five default identifiers for user accounts to this collection.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="a195c-123">请参阅</span><span class="sxs-lookup"><span data-stu-id="a195c-123">See also</span></span>
- <xref:System.ServiceModel.Activation.Configuration.NetTcpSection.AllowAccounts%2A>
- <xref:System.ServiceModel.Activation.Configuration.NetPipeSection.AllowAccounts%2A>
- <xref:System.ServiceModel.Activation.Configuration.SecurityIdentifierElementCollection>
- <xref:System.ServiceModel.Activation.Configuration.SecurityIdentifierElement>
