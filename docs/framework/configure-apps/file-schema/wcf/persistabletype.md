---
title: '&lt;persistableType&gt;'
ms.date: 03/30/2017
ms.assetid: e5425fe6-523a-4076-aab4-2c2515b1d830
ms.openlocfilehash: 92c59b3804e22c62340acccc1e12e594203c8e8b
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/09/2019
ms.locfileid: "54145414"
---
# <a name="ltpersistabletypegt"></a><span data-ttu-id="50f21-102">&lt;persistableType&gt;</span><span class="sxs-lookup"><span data-stu-id="50f21-102">&lt;persistableType&gt;</span></span>
<span data-ttu-id="50f21-103">指定所有永久类型。</span><span class="sxs-lookup"><span data-stu-id="50f21-103">Specifies all the persistable types.</span></span>  
  
 <span data-ttu-id="50f21-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="50f21-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="50f21-105">\<comContracts></span><span class="sxs-lookup"><span data-stu-id="50f21-105">\<comContracts></span></span>  
<span data-ttu-id="50f21-106">\<comContract ></span><span class="sxs-lookup"><span data-stu-id="50f21-106">\<comContract></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="50f21-107">语法</span><span class="sxs-lookup"><span data-stu-id="50f21-107">Syntax</span></span>  
  
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
  
## <a name="type"></a><span data-ttu-id="50f21-108">类型</span><span class="sxs-lookup"><span data-stu-id="50f21-108">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="50f21-109">特性和元素</span><span class="sxs-lookup"><span data-stu-id="50f21-109">Attributes and Elements</span></span>  
 <span data-ttu-id="50f21-110">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="50f21-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="50f21-111">特性</span><span class="sxs-lookup"><span data-stu-id="50f21-111">Attributes</span></span>  
  
|<span data-ttu-id="50f21-112">特性</span><span class="sxs-lookup"><span data-stu-id="50f21-112">Attribute</span></span>|<span data-ttu-id="50f21-113">描述</span><span class="sxs-lookup"><span data-stu-id="50f21-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="50f21-114">id</span><span class="sxs-lookup"><span data-stu-id="50f21-114">id</span></span>|<span data-ttu-id="50f21-115">一个必需的属性，包含一个指定持久类型唯一标识符的字符串。</span><span class="sxs-lookup"><span data-stu-id="50f21-115">A required attribute that contains a string that specifies a unique identifier for a persistable type.</span></span>|  
|<span data-ttu-id="50f21-116">name</span><span class="sxs-lookup"><span data-stu-id="50f21-116">name</span></span>|<span data-ttu-id="50f21-117">一个可选属性，包含一个指定持久类型名称的字符串。</span><span class="sxs-lookup"><span data-stu-id="50f21-117">An optional attribute that contains a string that specifies the name of the persistable type.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="50f21-118">子元素</span><span class="sxs-lookup"><span data-stu-id="50f21-118">Child Elements</span></span>  
 <span data-ttu-id="50f21-119">无</span><span class="sxs-lookup"><span data-stu-id="50f21-119">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="50f21-120">父元素</span><span class="sxs-lookup"><span data-stu-id="50f21-120">Parent Elements</span></span>  
  
|<span data-ttu-id="50f21-121">元素</span><span class="sxs-lookup"><span data-stu-id="50f21-121">Element</span></span>|<span data-ttu-id="50f21-122">描述</span><span class="sxs-lookup"><span data-stu-id="50f21-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="50f21-123">\<persistableTypes></span><span class="sxs-lookup"><span data-stu-id="50f21-123">\<persistableTypes></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/persistabletypes.md)|<span data-ttu-id="50f21-124">一个 `persistableType` 元素集合。</span><span class="sxs-lookup"><span data-stu-id="50f21-124">A collection of `persistableType` elements.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="50f21-125">请参阅</span><span class="sxs-lookup"><span data-stu-id="50f21-125">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.ComPersistableTypeElementCollection>  
 <xref:System.ServiceModel.Configuration.ComPersistableTypeElement>  
 [<span data-ttu-id="50f21-126">\<comContracts></span><span class="sxs-lookup"><span data-stu-id="50f21-126">\<comContracts></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/comcontracts.md)  
 [<span data-ttu-id="50f21-127">与 COM+ 应用程序集成</span><span class="sxs-lookup"><span data-stu-id="50f21-127">Integrating with COM+ Applications</span></span>](../../../../../docs/framework/wcf/feature-details/integrating-with-com-plus-applications.md)  
 [<span data-ttu-id="50f21-128">如何：配置 COM + 服务设置</span><span class="sxs-lookup"><span data-stu-id="50f21-128">How to: Configure COM+ Service Settings</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-configure-com-service-settings.md)
