---
title: <add> 的 <transportConfigurationType>
ms.date: 03/30/2017
ms.assetid: 03d79db9-571d-4534-acef-d05e5467b257
ms.openlocfilehash: adf4cd7f02db6535c5950443d09476a9a5ff63fb
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/10/2019
ms.locfileid: "70850320"
---
# <a name="add-of-transportconfigurationtype"></a><span data-ttu-id="99247-102">\<添加 transportConfigurationType > \<的 ></span><span class="sxs-lookup"><span data-stu-id="99247-102">\<add> of \<transportConfigurationType></span></span>
<span data-ttu-id="99247-103">此元素是一个键/值对，可标识特定传输的类型。</span><span class="sxs-lookup"><span data-stu-id="99247-103">This element is a key/value pair, which identifies the type of a particular transport.</span></span>  
  
<span data-ttu-id="99247-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="99247-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="99247-105">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="99247-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="99247-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<serviceHostingEnvironment >** ](servicehostingenvironment.md)</span><span class="sxs-lookup"><span data-stu-id="99247-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceHostingEnvironment>**](servicehostingenvironment.md)</span></span>\
<span data-ttu-id="99247-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<transportConfigurationTypes >** ](transportconfigurationtypes.md)</span><span class="sxs-lookup"><span data-stu-id="99247-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<transportConfigurationTypes>**](transportconfigurationtypes.md)</span></span>\
<span data-ttu-id="99247-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<添加 >**</span><span class="sxs-lookup"><span data-stu-id="99247-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="99247-109">语法</span><span class="sxs-lookup"><span data-stu-id="99247-109">Syntax</span></span>  
  
```xml  
<serviceHostingEnvironment>
  <transportConfigurationTypes>
    <add name="String"
         transportConfigurationType="String" />
  </transportConfigurationTypes>
</serviceHostingEnvironment>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="99247-110">特性和元素</span><span class="sxs-lookup"><span data-stu-id="99247-110">Attributes and Elements</span></span>  
 <span data-ttu-id="99247-111">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="99247-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="99247-112">特性</span><span class="sxs-lookup"><span data-stu-id="99247-112">Attributes</span></span>  
  
|<span data-ttu-id="99247-113">特性</span><span class="sxs-lookup"><span data-stu-id="99247-113">Attribute</span></span>|<span data-ttu-id="99247-114">描述</span><span class="sxs-lookup"><span data-stu-id="99247-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="99247-115">NAME</span><span class="sxs-lookup"><span data-stu-id="99247-115">name</span></span>|<span data-ttu-id="99247-116">必需的字符串属性。</span><span class="sxs-lookup"><span data-stu-id="99247-116">Required String attribute.</span></span><br /><br /> <span data-ttu-id="99247-117">包含一个唯一标识传输类型的用户定义的键。</span><span class="sxs-lookup"><span data-stu-id="99247-117">Contains a user-defined key that uniquely identifies the transport type.</span></span>|  
|<span data-ttu-id="99247-118">transportConfigurationType</span><span class="sxs-lookup"><span data-stu-id="99247-118">transportConfigurationType</span></span>|<span data-ttu-id="99247-119">一个包含实现特定传输的类型的字符串。</span><span class="sxs-lookup"><span data-stu-id="99247-119">A string that contains the type that implements the specific transport.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="99247-120">子元素</span><span class="sxs-lookup"><span data-stu-id="99247-120">Child Elements</span></span>  
 <span data-ttu-id="99247-121">无</span><span class="sxs-lookup"><span data-stu-id="99247-121">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="99247-122">父元素</span><span class="sxs-lookup"><span data-stu-id="99247-122">Parent Elements</span></span>  
  
|<span data-ttu-id="99247-123">元素</span><span class="sxs-lookup"><span data-stu-id="99247-123">Element</span></span>|<span data-ttu-id="99247-124">描述</span><span class="sxs-lookup"><span data-stu-id="99247-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="99247-125">\<transportConfigurationTypes></span><span class="sxs-lookup"><span data-stu-id="99247-125">\<transportConfigurationTypes></span></span>](transportconfigurationtypes.md)|<span data-ttu-id="99247-126">一个实现特定传输的类型的集合。</span><span class="sxs-lookup"><span data-stu-id="99247-126">A collection of types that implement the specific transport.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="99247-127">示例</span><span class="sxs-lookup"><span data-stu-id="99247-127">Example</span></span>  
  
```xml  
<serviceHostingEnvironment>
  <transportConfigurationTypes>
    <add name="net.udp"
         transportConfigurationType="Microsoft.ServiceModel.Samples.Hosting.HostedUdpTransportConfiguration, UdpActivation, Version=1.0.0.0, Culture=neutral, PublicKeyToken=6fa904d2da1848d6" />
  </transportConfigurationTypes>
</serviceHostingEnvironment>
```  
  
## <a name="see-also"></a><span data-ttu-id="99247-128">请参阅</span><span class="sxs-lookup"><span data-stu-id="99247-128">See also</span></span>

- <xref:System.ServiceModel.Configuration.TransportConfigurationTypeElement>
- <xref:System.ServiceModel.Configuration.ServiceHostingEnvironmentSection>
- <xref:System.ServiceModel.ServiceHostingEnvironment>
- [<span data-ttu-id="99247-129">承载</span><span class="sxs-lookup"><span data-stu-id="99247-129">Hosting</span></span>](../../../wcf/feature-details/hosting.md)
