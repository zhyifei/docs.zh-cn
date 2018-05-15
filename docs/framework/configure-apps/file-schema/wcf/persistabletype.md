---
title: '&lt;persistableType&gt;'
ms.date: 03/30/2017
ms.assetid: e5425fe6-523a-4076-aab4-2c2515b1d830
ms.openlocfilehash: 23724957398ed1ade2c81a3932e9773d7cf4c642
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
---
# <a name="ltpersistabletypegt"></a><span data-ttu-id="26f9a-102">&lt;persistableType&gt;</span><span class="sxs-lookup"><span data-stu-id="26f9a-102">&lt;persistableType&gt;</span></span>
<span data-ttu-id="26f9a-103">指定所有永久类型。</span><span class="sxs-lookup"><span data-stu-id="26f9a-103">Specifies all the persistable types.</span></span>  
  
 <span data-ttu-id="26f9a-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="26f9a-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="26f9a-105">\<comContracts></span><span class="sxs-lookup"><span data-stu-id="26f9a-105">\<comContracts></span></span>  
<span data-ttu-id="26f9a-106">\<comContract ></span><span class="sxs-lookup"><span data-stu-id="26f9a-106">\<comContract></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="26f9a-107">语法</span><span class="sxs-lookup"><span data-stu-id="26f9a-107">Syntax</span></span>  
  
```xml  
<comContracts>  
  <comContract>  
      <persistableTypes>  
         <persistableType id="string"  
            name="string">  
         </persistableType>  
      </persistableTypes>  
  </comContract>  
</comContracts>  
```  
  
## <a name="type"></a><span data-ttu-id="26f9a-108">类型</span><span class="sxs-lookup"><span data-stu-id="26f9a-108">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="26f9a-109">特性和元素</span><span class="sxs-lookup"><span data-stu-id="26f9a-109">Attributes and Elements</span></span>  
 <span data-ttu-id="26f9a-110">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="26f9a-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="26f9a-111">特性</span><span class="sxs-lookup"><span data-stu-id="26f9a-111">Attributes</span></span>  
  
|<span data-ttu-id="26f9a-112">特性</span><span class="sxs-lookup"><span data-stu-id="26f9a-112">Attribute</span></span>|<span data-ttu-id="26f9a-113">描述</span><span class="sxs-lookup"><span data-stu-id="26f9a-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="26f9a-114">id</span><span class="sxs-lookup"><span data-stu-id="26f9a-114">id</span></span>|<span data-ttu-id="26f9a-115">一个必需的属性，包含一个指定持久类型唯一标识符的字符串。</span><span class="sxs-lookup"><span data-stu-id="26f9a-115">A required attribute that contains a string that specifies a unique identifier for a persistable type.</span></span>|  
|<span data-ttu-id="26f9a-116">name</span><span class="sxs-lookup"><span data-stu-id="26f9a-116">name</span></span>|<span data-ttu-id="26f9a-117">一个可选属性，包含一个指定持久类型名称的字符串。</span><span class="sxs-lookup"><span data-stu-id="26f9a-117">An optional attribute that contains a string that specifies the name of the persistable type.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="26f9a-118">子元素</span><span class="sxs-lookup"><span data-stu-id="26f9a-118">Child Elements</span></span>  
 <span data-ttu-id="26f9a-119">无</span><span class="sxs-lookup"><span data-stu-id="26f9a-119">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="26f9a-120">父元素</span><span class="sxs-lookup"><span data-stu-id="26f9a-120">Parent Elements</span></span>  
  
|<span data-ttu-id="26f9a-121">元素</span><span class="sxs-lookup"><span data-stu-id="26f9a-121">Element</span></span>|<span data-ttu-id="26f9a-122">描述</span><span class="sxs-lookup"><span data-stu-id="26f9a-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="26f9a-123">\<persistableTypes></span><span class="sxs-lookup"><span data-stu-id="26f9a-123">\<persistableTypes></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/persistabletypes.md)|<span data-ttu-id="26f9a-124">一个 `persistableType` 元素集合。</span><span class="sxs-lookup"><span data-stu-id="26f9a-124">A collection of `persistableType` elements.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="26f9a-125">请参阅</span><span class="sxs-lookup"><span data-stu-id="26f9a-125">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.ComPersistableTypeElementCollection>  
 <xref:System.ServiceModel.Configuration.ComPersistableTypeElement>  
 [<span data-ttu-id="26f9a-126">\<comContracts></span><span class="sxs-lookup"><span data-stu-id="26f9a-126">\<comContracts></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/comcontracts.md)  
 [<span data-ttu-id="26f9a-127">与 COM+ 应用程序集成</span><span class="sxs-lookup"><span data-stu-id="26f9a-127">Integrating with COM+ Applications</span></span>](../../../../../docs/framework/wcf/feature-details/integrating-with-com-plus-applications.md)  
 [<span data-ttu-id="26f9a-128">如何：配置 COM+ 服务设置</span><span class="sxs-lookup"><span data-stu-id="26f9a-128">How to: Configure COM+ Service Settings</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-configure-com-service-settings.md)
