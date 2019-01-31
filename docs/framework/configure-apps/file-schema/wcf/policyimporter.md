---
title: <policyImporter>
ms.date: 03/30/2017
ms.assetid: b0d03456-546f-44bb-ab12-1b2ce7f98fca
ms.openlocfilehash: ab9193d5974ccffcbfa3e741ac4d32ff357ed372
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/30/2019
ms.locfileid: "55269232"
---
# <a name="policyimporter"></a><span data-ttu-id="26c4c-101">\<policyImporter></span><span class="sxs-lookup"><span data-stu-id="26c4c-101">\<policyImporter></span></span>
<span data-ttu-id="26c4c-102">指定一个策略导入程序，用于控制有关绑定的自定义策略断言的导入。</span><span class="sxs-lookup"><span data-stu-id="26c4c-102">Specifies a policy importer that controls the import of custom policy assertions about bindings.</span></span>  
  
 <span data-ttu-id="26c4c-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="26c4c-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="26c4c-104">\<client></span><span class="sxs-lookup"><span data-stu-id="26c4c-104">\<client></span></span>  
<span data-ttu-id="26c4c-105">\<metadata></span><span class="sxs-lookup"><span data-stu-id="26c4c-105">\<metadata></span></span>  
<span data-ttu-id="26c4c-106">\<policyImporters></span><span class="sxs-lookup"><span data-stu-id="26c4c-106">\<policyImporters></span></span>  
<span data-ttu-id="26c4c-107">\<policyImporter></span><span class="sxs-lookup"><span data-stu-id="26c4c-107">\<policyImporter></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="26c4c-108">语法</span><span class="sxs-lookup"><span data-stu-id="26c4c-108">Syntax</span></span>  
  
```xml  
<metadata>
  <policyImporters>
    <policyImporter type="String" />
  </policyImporters>
</metadata>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="26c4c-109">特性和元素</span><span class="sxs-lookup"><span data-stu-id="26c4c-109">Attributes and Elements</span></span>  
 <span data-ttu-id="26c4c-110">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="26c4c-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="26c4c-111">特性</span><span class="sxs-lookup"><span data-stu-id="26c4c-111">Attributes</span></span>  
  
|<span data-ttu-id="26c4c-112">特性</span><span class="sxs-lookup"><span data-stu-id="26c4c-112">Attribute</span></span>|<span data-ttu-id="26c4c-113">描述</span><span class="sxs-lookup"><span data-stu-id="26c4c-113">Description</span></span>|  
|---------------|-----------------|  
|`type`|<span data-ttu-id="26c4c-114">此元素的类型。</span><span class="sxs-lookup"><span data-stu-id="26c4c-114">The type of this element.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="26c4c-115">子元素</span><span class="sxs-lookup"><span data-stu-id="26c4c-115">Child Elements</span></span>  
 <span data-ttu-id="26c4c-116">无</span><span class="sxs-lookup"><span data-stu-id="26c4c-116">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="26c4c-117">父元素</span><span class="sxs-lookup"><span data-stu-id="26c4c-117">Parent Elements</span></span>  
  
|<span data-ttu-id="26c4c-118">元素</span><span class="sxs-lookup"><span data-stu-id="26c4c-118">Element</span></span>|<span data-ttu-id="26c4c-119">描述</span><span class="sxs-lookup"><span data-stu-id="26c4c-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="26c4c-120">\<policyImporters></span><span class="sxs-lookup"><span data-stu-id="26c4c-120">\<policyImporters></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/policyimporters.md)|<span data-ttu-id="26c4c-121">指定用于控制有关绑定的自定义策略断言的导入的所有策略导入程序。</span><span class="sxs-lookup"><span data-stu-id="26c4c-121">Specifies all the policy importers that control the import of custom policy assertions about bindings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="26c4c-122">备注</span><span class="sxs-lookup"><span data-stu-id="26c4c-122">Remarks</span></span>  
 <span data-ttu-id="26c4c-123">策略导入程序用于搜索有关绑定功能的自定义策略断言，并附加一个实现断言所需功能的自定义绑定元素。</span><span class="sxs-lookup"><span data-stu-id="26c4c-123">A policy importer is used to search custom policy assertions about binding features, as well as attach a custom binding element that implements the features the assertion requires.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="26c4c-124">请参阅</span><span class="sxs-lookup"><span data-stu-id="26c4c-124">See also</span></span>
- <xref:System.ServiceModel.Configuration.PolicyImporterElementCollection>
- <xref:System.ServiceModel.Configuration.PolicyImporterElement>
- <xref:System.ServiceModel.Configuration.MetadataElement>
- <xref:System.ServiceModel.Description.MetadataImporter>
- [<span data-ttu-id="26c4c-125">WCF 客户端配置</span><span class="sxs-lookup"><span data-stu-id="26c4c-125">WCF Client Configuration</span></span>](../../../../../docs/framework/wcf/feature-details/client-configuration.md)
- [<span data-ttu-id="26c4c-126">客户端</span><span class="sxs-lookup"><span data-stu-id="26c4c-126">Clients</span></span>](../../../../../docs/framework/wcf/feature-details/clients.md)
