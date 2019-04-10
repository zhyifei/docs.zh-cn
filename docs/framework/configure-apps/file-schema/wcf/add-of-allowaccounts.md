---
title: <add> 的 <allowAccounts>
ms.date: 03/30/2017
ms.assetid: 763c7b1f-e7b0-4d99-a42c-4506fcb8da00
ms.openlocfilehash: 1c6764b37b2aa5349b8ccf63e6b7c2bc580b69b9
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59186597"
---
# <a name="add-of-allowaccounts"></a><span data-ttu-id="ac1b0-102">\<添加 > 的\<allowAccounts ></span><span class="sxs-lookup"><span data-stu-id="ac1b0-102">\<add> of \<allowAccounts></span></span>
<span data-ttu-id="ac1b0-103">指定进程的承载 WCF 服务并被授予对共享服务的连接访问权限的用户的帐户。</span><span class="sxs-lookup"><span data-stu-id="ac1b0-103">Specifies a user account for processes that host WCF services, and are granted connection access to the sharing service.</span></span>  
  
 <span data-ttu-id="ac1b0-104">\<system.serviceModel.activation></span><span class="sxs-lookup"><span data-stu-id="ac1b0-104">\<system.serviceModel.activation></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ac1b0-105">语法</span><span class="sxs-lookup"><span data-stu-id="ac1b0-105">Syntax</span></span>  
  
```xml  
<allowAccounts>
  <add securityIdentifier="String" />
</allowAccounts>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ac1b0-106">特性和元素</span><span class="sxs-lookup"><span data-stu-id="ac1b0-106">Attributes and Elements</span></span>  
 <span data-ttu-id="ac1b0-107">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="ac1b0-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ac1b0-108">特性</span><span class="sxs-lookup"><span data-stu-id="ac1b0-108">Attributes</span></span>  
  
|<span data-ttu-id="ac1b0-109">特性</span><span class="sxs-lookup"><span data-stu-id="ac1b0-109">Attribute</span></span>|<span data-ttu-id="ac1b0-110">描述</span><span class="sxs-lookup"><span data-stu-id="ac1b0-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="ac1b0-111">securityIdentifier</span><span class="sxs-lookup"><span data-stu-id="ac1b0-111">securityIdentifier</span></span>|<span data-ttu-id="ac1b0-112">一个字符串，指定用于标识用户帐户的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="ac1b0-112">A string that specifies a unique identifier used to identify a user account.</span></span> <span data-ttu-id="ac1b0-113">默认值为 LocalSystem、Administrators、NS、LS 和 IIS_USRS。</span><span class="sxs-lookup"><span data-stu-id="ac1b0-113">The default values are LocalSystem, Administrators, NS, LS, and IIS_USRS.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ac1b0-114">子元素</span><span class="sxs-lookup"><span data-stu-id="ac1b0-114">Child Elements</span></span>  
 <span data-ttu-id="ac1b0-115">无。</span><span class="sxs-lookup"><span data-stu-id="ac1b0-115">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="ac1b0-116">父元素</span><span class="sxs-lookup"><span data-stu-id="ac1b0-116">Parent Elements</span></span>  
  
|<span data-ttu-id="ac1b0-117">元素</span><span class="sxs-lookup"><span data-stu-id="ac1b0-117">Element</span></span>|<span data-ttu-id="ac1b0-118">描述</span><span class="sxs-lookup"><span data-stu-id="ac1b0-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ac1b0-119">\<allowAccounts></span><span class="sxs-lookup"><span data-stu-id="ac1b0-119">\<allowAccounts></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/allowaccounts.md)|<span data-ttu-id="ac1b0-120">包含的配置元素的集合`securityIdentifier`属性指定的进程的承载 WCF 服务并被授予对共享服务的连接访问权限的用户帐户。</span><span class="sxs-lookup"><span data-stu-id="ac1b0-120">A collection of configuration elements that contain a `securityIdentifier` attribute to specify user accounts for processes that host WCF services, and are granted connection access to the sharing service.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="ac1b0-121">示例</span><span class="sxs-lookup"><span data-stu-id="ac1b0-121">Example</span></span>  
 <span data-ttu-id="ac1b0-122">下面的配置示例将用户帐户的五个默认标识符添加到此集合中。</span><span class="sxs-lookup"><span data-stu-id="ac1b0-122">The following configuration example adds the five default identifiers for user accounts to this collection.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="ac1b0-123">请参阅</span><span class="sxs-lookup"><span data-stu-id="ac1b0-123">See also</span></span>

- <xref:System.ServiceModel.Activation.Configuration.NetTcpSection.AllowAccounts%2A>
- <xref:System.ServiceModel.Activation.Configuration.NetPipeSection.AllowAccounts%2A>
- <xref:System.ServiceModel.Activation.Configuration.SecurityIdentifierElementCollection>
- <xref:System.ServiceModel.Activation.Configuration.SecurityIdentifierElement>
