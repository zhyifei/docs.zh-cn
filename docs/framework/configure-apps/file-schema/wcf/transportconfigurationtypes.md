---
title: <transportConfigurationTypes>
ms.date: 03/30/2017
ms.assetid: 929c8b0a-5460-4f66-a098-2cb8d4e10b69
ms.openlocfilehash: b3683a198ec403fb9966bb902c936108fd043bfa
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61788240"
---
# <a name="transportconfigurationtypes"></a><span data-ttu-id="47c25-101">\<transportConfigurationTypes></span><span class="sxs-lookup"><span data-stu-id="47c25-101">\<transportConfigurationTypes></span></span>
<span data-ttu-id="47c25-102">表示一个配置元素集合，这些元素标识了特定传输的类型。</span><span class="sxs-lookup"><span data-stu-id="47c25-102">Represents a collection of configuration elements that identify the type of a particular transport.</span></span> <span data-ttu-id="47c25-103">这可以用于添加自定义 WAS 协议。</span><span class="sxs-lookup"><span data-stu-id="47c25-103">This can be used to add custom WAS protocols.</span></span>  
  
 <span data-ttu-id="47c25-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="47c25-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="47c25-105">\<ServiceHostingEnvironment></span><span class="sxs-lookup"><span data-stu-id="47c25-105">\<ServiceHostingEnvironment></span></span>  
<span data-ttu-id="47c25-106">\<transportConfigurationTypes></span><span class="sxs-lookup"><span data-stu-id="47c25-106">\<transportConfigurationTypes></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="47c25-107">语法</span><span class="sxs-lookup"><span data-stu-id="47c25-107">Syntax</span></span>  
  
```xml  
<serviceHostingEnvironment>
  <transportConfigurationTypes>
    <add name="String"
         transportConfigurationType="String" />
  </transportConfigurationTypes>
</serviceHostingEnvironment>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="47c25-108">特性和元素</span><span class="sxs-lookup"><span data-stu-id="47c25-108">Attributes and Elements</span></span>  
 <span data-ttu-id="47c25-109">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="47c25-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="47c25-110">特性</span><span class="sxs-lookup"><span data-stu-id="47c25-110">Attributes</span></span>  
  
|<span data-ttu-id="47c25-111">特性</span><span class="sxs-lookup"><span data-stu-id="47c25-111">Attribute</span></span>|<span data-ttu-id="47c25-112">描述</span><span class="sxs-lookup"><span data-stu-id="47c25-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="47c25-113">name</span><span class="sxs-lookup"><span data-stu-id="47c25-113">name</span></span>|<span data-ttu-id="47c25-114">传输的名称</span><span class="sxs-lookup"><span data-stu-id="47c25-114">The name of the transport</span></span>|  
|<span data-ttu-id="47c25-115">transportConfigurationType</span><span class="sxs-lookup"><span data-stu-id="47c25-115">transportConfigurationType</span></span>|<span data-ttu-id="47c25-116">实现传输的类型</span><span class="sxs-lookup"><span data-stu-id="47c25-116">The type that implements the transport</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="47c25-117">子元素</span><span class="sxs-lookup"><span data-stu-id="47c25-117">Child Elements</span></span>  
  
|<span data-ttu-id="47c25-118">元素</span><span class="sxs-lookup"><span data-stu-id="47c25-118">Element</span></span>|<span data-ttu-id="47c25-119">描述</span><span class="sxs-lookup"><span data-stu-id="47c25-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="47c25-120">\<add></span><span class="sxs-lookup"><span data-stu-id="47c25-120">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-transportconfigurationtype.md)|<span data-ttu-id="47c25-121">添加一个用于标识特定传输的类型的配置元素。</span><span class="sxs-lookup"><span data-stu-id="47c25-121">Adds a configuration element that identifies the type of a particular transport.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="47c25-122">父元素</span><span class="sxs-lookup"><span data-stu-id="47c25-122">Parent Elements</span></span>  
  
|<span data-ttu-id="47c25-123">元素</span><span class="sxs-lookup"><span data-stu-id="47c25-123">Element</span></span>|<span data-ttu-id="47c25-124">描述</span><span class="sxs-lookup"><span data-stu-id="47c25-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="47c25-125">\<serviceHostingEnvironment></span><span class="sxs-lookup"><span data-stu-id="47c25-125">\<serviceHostingEnvironment></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicehostingenvironment.md)|<span data-ttu-id="47c25-126">定义服务承载环境要为特定传输实例化的类型。</span><span class="sxs-lookup"><span data-stu-id="47c25-126">Defines the type the service hosting environment instantiates for a particular transport.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="47c25-127">请参阅</span><span class="sxs-lookup"><span data-stu-id="47c25-127">See also</span></span>

- <xref:System.ServiceModel.Configuration.ServiceHostingEnvironmentSection>
- <xref:System.ServiceModel.ServiceHostingEnvironment>
- <xref:System.ServiceModel.Configuration.TransportConfigurationTypeElementCollection>
- [<span data-ttu-id="47c25-128">承载</span><span class="sxs-lookup"><span data-stu-id="47c25-128">Hosting</span></span>](../../../../../docs/framework/wcf/feature-details/hosting.md)
