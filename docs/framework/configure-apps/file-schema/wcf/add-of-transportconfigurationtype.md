---
title: <add> 的 <transportConfigurationType>
ms.date: 03/30/2017
ms.assetid: 03d79db9-571d-4534-acef-d05e5467b257
ms.openlocfilehash: c71a58b13e89bedb5eed24d784c82fb1525f7625
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59126719"
---
# <a name="add-of-transportconfigurationtype"></a><span data-ttu-id="d0c26-102">\<add> of \<transportConfigurationType></span><span class="sxs-lookup"><span data-stu-id="d0c26-102">\<add> of \<transportConfigurationType></span></span>
<span data-ttu-id="d0c26-103">此元素是一个键/值对，可标识特定传输的类型。</span><span class="sxs-lookup"><span data-stu-id="d0c26-103">This element is a key/value pair, which identifies the type of a particular transport.</span></span>  
  
 <span data-ttu-id="d0c26-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="d0c26-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="d0c26-105">\<ServiceHostingEnvironment></span><span class="sxs-lookup"><span data-stu-id="d0c26-105">\<ServiceHostingEnvironment></span></span>  
<span data-ttu-id="d0c26-106">\<transportConfigurationTypes></span><span class="sxs-lookup"><span data-stu-id="d0c26-106">\<transportConfigurationTypes></span></span>  
<span data-ttu-id="d0c26-107">\<add></span><span class="sxs-lookup"><span data-stu-id="d0c26-107">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d0c26-108">语法</span><span class="sxs-lookup"><span data-stu-id="d0c26-108">Syntax</span></span>  
  
```xml  
<serviceHostingEnvironment>
  <transportConfigurationTypes>
    <add name="String"
         transportConfigurationType="String" />
  </transportConfigurationTypes>
</serviceHostingEnvironment>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d0c26-109">特性和元素</span><span class="sxs-lookup"><span data-stu-id="d0c26-109">Attributes and Elements</span></span>  
 <span data-ttu-id="d0c26-110">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="d0c26-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d0c26-111">特性</span><span class="sxs-lookup"><span data-stu-id="d0c26-111">Attributes</span></span>  
  
|<span data-ttu-id="d0c26-112">特性</span><span class="sxs-lookup"><span data-stu-id="d0c26-112">Attribute</span></span>|<span data-ttu-id="d0c26-113">描述</span><span class="sxs-lookup"><span data-stu-id="d0c26-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="d0c26-114">name</span><span class="sxs-lookup"><span data-stu-id="d0c26-114">name</span></span>|<span data-ttu-id="d0c26-115">必需的字符串属性。</span><span class="sxs-lookup"><span data-stu-id="d0c26-115">Required String attribute.</span></span><br /><br /> <span data-ttu-id="d0c26-116">包含一个唯一标识传输类型的用户定义的键。</span><span class="sxs-lookup"><span data-stu-id="d0c26-116">Contains a user-defined key that uniquely identifies the transport type.</span></span>|  
|<span data-ttu-id="d0c26-117">transportConfigurationType</span><span class="sxs-lookup"><span data-stu-id="d0c26-117">transportConfigurationType</span></span>|<span data-ttu-id="d0c26-118">一个包含实现特定传输的类型的字符串。</span><span class="sxs-lookup"><span data-stu-id="d0c26-118">A string that contains the type that implements the specific transport.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d0c26-119">子元素</span><span class="sxs-lookup"><span data-stu-id="d0c26-119">Child Elements</span></span>  
 <span data-ttu-id="d0c26-120">None</span><span class="sxs-lookup"><span data-stu-id="d0c26-120">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="d0c26-121">父元素</span><span class="sxs-lookup"><span data-stu-id="d0c26-121">Parent Elements</span></span>  
  
|<span data-ttu-id="d0c26-122">元素</span><span class="sxs-lookup"><span data-stu-id="d0c26-122">Element</span></span>|<span data-ttu-id="d0c26-123">描述</span><span class="sxs-lookup"><span data-stu-id="d0c26-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d0c26-124">\<transportConfigurationTypes></span><span class="sxs-lookup"><span data-stu-id="d0c26-124">\<transportConfigurationTypes></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/transportconfigurationtypes.md)|<span data-ttu-id="d0c26-125">一个实现特定传输的类型的集合。</span><span class="sxs-lookup"><span data-stu-id="d0c26-125">A collection of types that implement the specific transport.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="d0c26-126">示例</span><span class="sxs-lookup"><span data-stu-id="d0c26-126">Example</span></span>  
  
```xml  
<serviceHostingEnvironment>
  <transportConfigurationTypes>
    <add name="net.udp"
         transportConfigurationType="Microsoft.ServiceModel.Samples.Hosting.HostedUdpTransportConfiguration, UdpActivation, Version=1.0.0.0, Culture=neutral, PublicKeyToken=6fa904d2da1848d6" />
  </transportConfigurationTypes>
</serviceHostingEnvironment>
```  
  
## <a name="see-also"></a><span data-ttu-id="d0c26-127">请参阅</span><span class="sxs-lookup"><span data-stu-id="d0c26-127">See also</span></span>

- <xref:System.ServiceModel.Configuration.TransportConfigurationTypeElement>
- <xref:System.ServiceModel.Configuration.ServiceHostingEnvironmentSection>
- <xref:System.ServiceModel.ServiceHostingEnvironment>
- [<span data-ttu-id="d0c26-128">承载</span><span class="sxs-lookup"><span data-stu-id="d0c26-128">Hosting</span></span>](../../../../../docs/framework/wcf/feature-details/hosting.md)
