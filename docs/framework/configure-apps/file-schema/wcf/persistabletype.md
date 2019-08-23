---
title: <persistableType>
ms.date: 03/30/2017
ms.assetid: e5425fe6-523a-4076-aab4-2c2515b1d830
ms.openlocfilehash: fcfd338e289b5151688724f0e84b6878707d32be
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69933826"
---
# <a name="persistabletype"></a><span data-ttu-id="4def0-101">\<persistableType></span><span class="sxs-lookup"><span data-stu-id="4def0-101">\<persistableType></span></span>
<span data-ttu-id="4def0-102">指定所有永久类型。</span><span class="sxs-lookup"><span data-stu-id="4def0-102">Specifies all the persistable types.</span></span>  
  
 <span data-ttu-id="4def0-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="4def0-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="4def0-104">\<comContracts></span><span class="sxs-lookup"><span data-stu-id="4def0-104">\<comContracts></span></span>  
<span data-ttu-id="4def0-105">\<comContract></span><span class="sxs-lookup"><span data-stu-id="4def0-105">\<comContract></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4def0-106">语法</span><span class="sxs-lookup"><span data-stu-id="4def0-106">Syntax</span></span>  
  
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
  
## <a name="type"></a><span data-ttu-id="4def0-107">类型</span><span class="sxs-lookup"><span data-stu-id="4def0-107">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4def0-108">特性和元素</span><span class="sxs-lookup"><span data-stu-id="4def0-108">Attributes and Elements</span></span>  
 <span data-ttu-id="4def0-109">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="4def0-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4def0-110">特性</span><span class="sxs-lookup"><span data-stu-id="4def0-110">Attributes</span></span>  
  
|<span data-ttu-id="4def0-111">特性</span><span class="sxs-lookup"><span data-stu-id="4def0-111">Attribute</span></span>|<span data-ttu-id="4def0-112">描述</span><span class="sxs-lookup"><span data-stu-id="4def0-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="4def0-113">id</span><span class="sxs-lookup"><span data-stu-id="4def0-113">id</span></span>|<span data-ttu-id="4def0-114">一个必需的属性，包含一个指定持久类型唯一标识符的字符串。</span><span class="sxs-lookup"><span data-stu-id="4def0-114">A required attribute that contains a string that specifies a unique identifier for a persistable type.</span></span>|  
|<span data-ttu-id="4def0-115">NAME</span><span class="sxs-lookup"><span data-stu-id="4def0-115">name</span></span>|<span data-ttu-id="4def0-116">一个可选属性，包含一个指定持久类型名称的字符串。</span><span class="sxs-lookup"><span data-stu-id="4def0-116">An optional attribute that contains a string that specifies the name of the persistable type.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="4def0-117">子元素</span><span class="sxs-lookup"><span data-stu-id="4def0-117">Child Elements</span></span>  
 <span data-ttu-id="4def0-118">无</span><span class="sxs-lookup"><span data-stu-id="4def0-118">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="4def0-119">父元素</span><span class="sxs-lookup"><span data-stu-id="4def0-119">Parent Elements</span></span>  
  
|<span data-ttu-id="4def0-120">元素</span><span class="sxs-lookup"><span data-stu-id="4def0-120">Element</span></span>|<span data-ttu-id="4def0-121">描述</span><span class="sxs-lookup"><span data-stu-id="4def0-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4def0-122">\<persistableTypes></span><span class="sxs-lookup"><span data-stu-id="4def0-122">\<persistableTypes></span></span>](persistabletypes.md)|<span data-ttu-id="4def0-123">一个 `persistableType` 元素集合。</span><span class="sxs-lookup"><span data-stu-id="4def0-123">A collection of `persistableType` elements.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="4def0-124">请参阅</span><span class="sxs-lookup"><span data-stu-id="4def0-124">See also</span></span>

- <xref:System.ServiceModel.Configuration.ComPersistableTypeElementCollection>
- <xref:System.ServiceModel.Configuration.ComPersistableTypeElement>
- [<span data-ttu-id="4def0-125">\<comContracts></span><span class="sxs-lookup"><span data-stu-id="4def0-125">\<comContracts></span></span>](comcontracts.md)
- [<span data-ttu-id="4def0-126">与 COM+ 应用程序集成</span><span class="sxs-lookup"><span data-stu-id="4def0-126">Integrating with COM+ Applications</span></span>](../../../wcf/feature-details/integrating-with-com-plus-applications.md)
- [<span data-ttu-id="4def0-127">如何：配置 COM + 服务设置</span><span class="sxs-lookup"><span data-stu-id="4def0-127">How to: Configure COM+ Service Settings</span></span>](../../../wcf/feature-details/how-to-configure-com-service-settings.md)
