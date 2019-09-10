---
title: <policyImporter>
ms.date: 03/30/2017
ms.assetid: b0d03456-546f-44bb-ab12-1b2ce7f98fca
ms.openlocfilehash: 4ef5890d52c3f2af42322f023b9a2a23cb583035
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/10/2019
ms.locfileid: "70855064"
---
# <a name="policyimporter"></a><span data-ttu-id="ddb05-101">\<policyImporter></span><span class="sxs-lookup"><span data-stu-id="ddb05-101">\<policyImporter></span></span>
<span data-ttu-id="ddb05-102">指定一个策略导入程序，用于控制有关绑定的自定义策略断言的导入。</span><span class="sxs-lookup"><span data-stu-id="ddb05-102">Specifies a policy importer that controls the import of custom policy assertions about bindings.</span></span>  
  
<span data-ttu-id="ddb05-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="ddb05-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="ddb05-104">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="ddb05-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="ddb05-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<客户端 >** ](client.md)</span><span class="sxs-lookup"><span data-stu-id="ddb05-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<client>**](client.md)</span></span>\
<span data-ttu-id="ddb05-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<元数据 >** ](metadata.md)</span><span class="sxs-lookup"><span data-stu-id="ddb05-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<metadata>**](metadata.md)</span></span>\
<span data-ttu-id="ddb05-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<policyImporters >** ](policyimporters.md)</span><span class="sxs-lookup"><span data-stu-id="ddb05-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<policyImporters>**](policyimporters.md)</span></span>  
<span data-ttu-id="ddb05-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<policyImporter >**</span><span class="sxs-lookup"><span data-stu-id="ddb05-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<policyImporter>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ddb05-109">语法</span><span class="sxs-lookup"><span data-stu-id="ddb05-109">Syntax</span></span>  
  
```xml  
<metadata>
  <policyImporters>
    <policyImporter type="String" />
  </policyImporters>
</metadata>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ddb05-110">特性和元素</span><span class="sxs-lookup"><span data-stu-id="ddb05-110">Attributes and Elements</span></span>  
 <span data-ttu-id="ddb05-111">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="ddb05-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ddb05-112">特性</span><span class="sxs-lookup"><span data-stu-id="ddb05-112">Attributes</span></span>  
  
|<span data-ttu-id="ddb05-113">特性</span><span class="sxs-lookup"><span data-stu-id="ddb05-113">Attribute</span></span>|<span data-ttu-id="ddb05-114">描述</span><span class="sxs-lookup"><span data-stu-id="ddb05-114">Description</span></span>|  
|---------------|-----------------|  
|`type`|<span data-ttu-id="ddb05-115">此元素的类型。</span><span class="sxs-lookup"><span data-stu-id="ddb05-115">The type of this element.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ddb05-116">子元素</span><span class="sxs-lookup"><span data-stu-id="ddb05-116">Child Elements</span></span>  
 <span data-ttu-id="ddb05-117">无</span><span class="sxs-lookup"><span data-stu-id="ddb05-117">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="ddb05-118">父元素</span><span class="sxs-lookup"><span data-stu-id="ddb05-118">Parent Elements</span></span>  
  
|<span data-ttu-id="ddb05-119">元素</span><span class="sxs-lookup"><span data-stu-id="ddb05-119">Element</span></span>|<span data-ttu-id="ddb05-120">描述</span><span class="sxs-lookup"><span data-stu-id="ddb05-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ddb05-121">\<policyImporters></span><span class="sxs-lookup"><span data-stu-id="ddb05-121">\<policyImporters></span></span>](policyimporters.md)|<span data-ttu-id="ddb05-122">指定用于控制有关绑定的自定义策略断言的导入的所有策略导入程序。</span><span class="sxs-lookup"><span data-stu-id="ddb05-122">Specifies all the policy importers that control the import of custom policy assertions about bindings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ddb05-123">备注</span><span class="sxs-lookup"><span data-stu-id="ddb05-123">Remarks</span></span>  
 <span data-ttu-id="ddb05-124">策略导入程序用于搜索有关绑定功能的自定义策略断言，并附加一个实现断言所需功能的自定义绑定元素。</span><span class="sxs-lookup"><span data-stu-id="ddb05-124">A policy importer is used to search custom policy assertions about binding features, as well as attach a custom binding element that implements the features the assertion requires.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ddb05-125">请参阅</span><span class="sxs-lookup"><span data-stu-id="ddb05-125">See also</span></span>

- <xref:System.ServiceModel.Configuration.PolicyImporterElementCollection>
- <xref:System.ServiceModel.Configuration.PolicyImporterElement>
- <xref:System.ServiceModel.Configuration.MetadataElement>
- <xref:System.ServiceModel.Description.MetadataImporter>
- [<span data-ttu-id="ddb05-126">WCF 客户端配置</span><span class="sxs-lookup"><span data-stu-id="ddb05-126">WCF Client Configuration</span></span>](../../../wcf/feature-details/client-configuration.md)
- [<span data-ttu-id="ddb05-127">客户端</span><span class="sxs-lookup"><span data-stu-id="ddb05-127">Clients</span></span>](../../../wcf/feature-details/clients.md)
