---
title: <persistableType>
ms.date: 03/30/2017
ms.assetid: e5425fe6-523a-4076-aab4-2c2515b1d830
ms.openlocfilehash: 939a29e90ee21e94ccb78842d6f7224e9a6288d0
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59083733"
---
# <a name="persistabletype"></a><span data-ttu-id="d60f4-101">\<persistableType></span><span class="sxs-lookup"><span data-stu-id="d60f4-101">\<persistableType></span></span>
<span data-ttu-id="d60f4-102">指定所有永久类型。</span><span class="sxs-lookup"><span data-stu-id="d60f4-102">Specifies all the persistable types.</span></span>  
  
 <span data-ttu-id="d60f4-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="d60f4-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="d60f4-104">\<comContracts></span><span class="sxs-lookup"><span data-stu-id="d60f4-104">\<comContracts></span></span>  
<span data-ttu-id="d60f4-105">\<comContract></span><span class="sxs-lookup"><span data-stu-id="d60f4-105">\<comContract></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d60f4-106">语法</span><span class="sxs-lookup"><span data-stu-id="d60f4-106">Syntax</span></span>  
  
```xml  
<comContracts>
  <comContract>
    <persistableTypes>
      <persistableType id="String"
                       name="String">
      </persistableType>
    </persistableTypes>
  </comContract>
</comContracts>
```  
  
## <a name="type"></a><span data-ttu-id="d60f4-107">类型</span><span class="sxs-lookup"><span data-stu-id="d60f4-107">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d60f4-108">特性和元素</span><span class="sxs-lookup"><span data-stu-id="d60f4-108">Attributes and Elements</span></span>  
 <span data-ttu-id="d60f4-109">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="d60f4-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d60f4-110">特性</span><span class="sxs-lookup"><span data-stu-id="d60f4-110">Attributes</span></span>  
  
|<span data-ttu-id="d60f4-111">特性</span><span class="sxs-lookup"><span data-stu-id="d60f4-111">Attribute</span></span>|<span data-ttu-id="d60f4-112">描述</span><span class="sxs-lookup"><span data-stu-id="d60f4-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="d60f4-113">id</span><span class="sxs-lookup"><span data-stu-id="d60f4-113">id</span></span>|<span data-ttu-id="d60f4-114">一个必需的属性，包含一个指定持久类型唯一标识符的字符串。</span><span class="sxs-lookup"><span data-stu-id="d60f4-114">A required attribute that contains a string that specifies a unique identifier for a persistable type.</span></span>|  
|<span data-ttu-id="d60f4-115">name</span><span class="sxs-lookup"><span data-stu-id="d60f4-115">name</span></span>|<span data-ttu-id="d60f4-116">一个可选属性，包含一个指定持久类型名称的字符串。</span><span class="sxs-lookup"><span data-stu-id="d60f4-116">An optional attribute that contains a string that specifies the name of the persistable type.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d60f4-117">子元素</span><span class="sxs-lookup"><span data-stu-id="d60f4-117">Child Elements</span></span>  
 <span data-ttu-id="d60f4-118">None</span><span class="sxs-lookup"><span data-stu-id="d60f4-118">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="d60f4-119">父元素</span><span class="sxs-lookup"><span data-stu-id="d60f4-119">Parent Elements</span></span>  
  
|<span data-ttu-id="d60f4-120">元素</span><span class="sxs-lookup"><span data-stu-id="d60f4-120">Element</span></span>|<span data-ttu-id="d60f4-121">描述</span><span class="sxs-lookup"><span data-stu-id="d60f4-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d60f4-122">\<persistableTypes></span><span class="sxs-lookup"><span data-stu-id="d60f4-122">\<persistableTypes></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/persistabletypes.md)|<span data-ttu-id="d60f4-123">一个 `persistableType` 元素集合。</span><span class="sxs-lookup"><span data-stu-id="d60f4-123">A collection of `persistableType` elements.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="d60f4-124">请参阅</span><span class="sxs-lookup"><span data-stu-id="d60f4-124">See also</span></span>

- <xref:System.ServiceModel.Configuration.ComPersistableTypeElementCollection>
- <xref:System.ServiceModel.Configuration.ComPersistableTypeElement>
- [<span data-ttu-id="d60f4-125">\<comContracts></span><span class="sxs-lookup"><span data-stu-id="d60f4-125">\<comContracts></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/comcontracts.md)
- [<span data-ttu-id="d60f4-126">与 COM+ 应用程序集成</span><span class="sxs-lookup"><span data-stu-id="d60f4-126">Integrating with COM+ Applications</span></span>](../../../../../docs/framework/wcf/feature-details/integrating-with-com-plus-applications.md)
- [<span data-ttu-id="d60f4-127">如何：配置 COM+ 服务设置</span><span class="sxs-lookup"><span data-stu-id="d60f4-127">How to: Configure COM+ Service Settings</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-configure-com-service-settings.md)
