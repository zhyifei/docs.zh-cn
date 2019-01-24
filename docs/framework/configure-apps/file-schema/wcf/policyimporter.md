---
title: '&lt;policyImporter&gt;'
ms.date: 03/30/2017
ms.assetid: b0d03456-546f-44bb-ab12-1b2ce7f98fca
ms.openlocfilehash: 4075f7fcb1c65da3d9e2e5e5dab52452ca2c9b60
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54632161"
---
# <a name="ltpolicyimportergt"></a><span data-ttu-id="81d03-102">&lt;policyImporter&gt;</span><span class="sxs-lookup"><span data-stu-id="81d03-102">&lt;policyImporter&gt;</span></span>
<span data-ttu-id="81d03-103">指定一个策略导入程序，用于控制有关绑定的自定义策略断言的导入。</span><span class="sxs-lookup"><span data-stu-id="81d03-103">Specifies a policy importer that controls the import of custom policy assertions about bindings.</span></span>  
  
 <span data-ttu-id="81d03-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="81d03-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="81d03-105">\<client></span><span class="sxs-lookup"><span data-stu-id="81d03-105">\<client></span></span>  
<span data-ttu-id="81d03-106">\<metadata></span><span class="sxs-lookup"><span data-stu-id="81d03-106">\<metadata></span></span>  
<span data-ttu-id="81d03-107">\<policyImporters></span><span class="sxs-lookup"><span data-stu-id="81d03-107">\<policyImporters></span></span>  
<span data-ttu-id="81d03-108">\<policyImporter></span><span class="sxs-lookup"><span data-stu-id="81d03-108">\<policyImporter></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="81d03-109">语法</span><span class="sxs-lookup"><span data-stu-id="81d03-109">Syntax</span></span>  
  
```xml  
<metadata>
  <policyImporters>
    <policyImporter type="String" />
  </policyImporters>
</metadata>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="81d03-110">特性和元素</span><span class="sxs-lookup"><span data-stu-id="81d03-110">Attributes and Elements</span></span>  
 <span data-ttu-id="81d03-111">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="81d03-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="81d03-112">特性</span><span class="sxs-lookup"><span data-stu-id="81d03-112">Attributes</span></span>  
  
|<span data-ttu-id="81d03-113">特性</span><span class="sxs-lookup"><span data-stu-id="81d03-113">Attribute</span></span>|<span data-ttu-id="81d03-114">描述</span><span class="sxs-lookup"><span data-stu-id="81d03-114">Description</span></span>|  
|---------------|-----------------|  
|`type`|<span data-ttu-id="81d03-115">此元素的类型。</span><span class="sxs-lookup"><span data-stu-id="81d03-115">The type of this element.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="81d03-116">子元素</span><span class="sxs-lookup"><span data-stu-id="81d03-116">Child Elements</span></span>  
 <span data-ttu-id="81d03-117">无</span><span class="sxs-lookup"><span data-stu-id="81d03-117">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="81d03-118">父元素</span><span class="sxs-lookup"><span data-stu-id="81d03-118">Parent Elements</span></span>  
  
|<span data-ttu-id="81d03-119">元素</span><span class="sxs-lookup"><span data-stu-id="81d03-119">Element</span></span>|<span data-ttu-id="81d03-120">描述</span><span class="sxs-lookup"><span data-stu-id="81d03-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="81d03-121">\<policyImporters></span><span class="sxs-lookup"><span data-stu-id="81d03-121">\<policyImporters></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/policyimporters.md)|<span data-ttu-id="81d03-122">指定用于控制有关绑定的自定义策略断言的导入的所有策略导入程序。</span><span class="sxs-lookup"><span data-stu-id="81d03-122">Specifies all the policy importers that control the import of custom policy assertions about bindings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="81d03-123">备注</span><span class="sxs-lookup"><span data-stu-id="81d03-123">Remarks</span></span>  
 <span data-ttu-id="81d03-124">策略导入程序用于搜索有关绑定功能的自定义策略断言，并附加一个实现断言所需功能的自定义绑定元素。</span><span class="sxs-lookup"><span data-stu-id="81d03-124">A policy importer is used to search custom policy assertions about binding features, as well as attach a custom binding element that implements the features the assertion requires.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="81d03-125">请参阅</span><span class="sxs-lookup"><span data-stu-id="81d03-125">See also</span></span>
- <xref:System.ServiceModel.Configuration.PolicyImporterElementCollection>
- <xref:System.ServiceModel.Configuration.PolicyImporterElement>
- <xref:System.ServiceModel.Configuration.MetadataElement>
- <xref:System.ServiceModel.Description.MetadataImporter>
- [<span data-ttu-id="81d03-126">WCF 客户端配置</span><span class="sxs-lookup"><span data-stu-id="81d03-126">WCF Client Configuration</span></span>](../../../../../docs/framework/wcf/feature-details/client-configuration.md)
- [<span data-ttu-id="81d03-127">客户端</span><span class="sxs-lookup"><span data-stu-id="81d03-127">Clients</span></span>](../../../../../docs/framework/wcf/feature-details/clients.md)
