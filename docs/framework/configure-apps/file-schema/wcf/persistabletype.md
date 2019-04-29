---
title: <persistableType>
ms.date: 03/30/2017
ms.assetid: e5425fe6-523a-4076-aab4-2c2515b1d830
ms.openlocfilehash: 939a29e90ee21e94ccb78842d6f7224e9a6288d0
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61783313"
---
# <a name="persistabletype"></a><span data-ttu-id="2df1f-101">\<persistableType></span><span class="sxs-lookup"><span data-stu-id="2df1f-101">\<persistableType></span></span>
<span data-ttu-id="2df1f-102">指定所有永久类型。</span><span class="sxs-lookup"><span data-stu-id="2df1f-102">Specifies all the persistable types.</span></span>  
  
 <span data-ttu-id="2df1f-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="2df1f-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="2df1f-104">\<comContracts></span><span class="sxs-lookup"><span data-stu-id="2df1f-104">\<comContracts></span></span>  
<span data-ttu-id="2df1f-105">\<comContract></span><span class="sxs-lookup"><span data-stu-id="2df1f-105">\<comContract></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2df1f-106">语法</span><span class="sxs-lookup"><span data-stu-id="2df1f-106">Syntax</span></span>  
  
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
  
## <a name="type"></a><span data-ttu-id="2df1f-107">类型</span><span class="sxs-lookup"><span data-stu-id="2df1f-107">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2df1f-108">特性和元素</span><span class="sxs-lookup"><span data-stu-id="2df1f-108">Attributes and Elements</span></span>  
 <span data-ttu-id="2df1f-109">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="2df1f-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2df1f-110">特性</span><span class="sxs-lookup"><span data-stu-id="2df1f-110">Attributes</span></span>  
  
|<span data-ttu-id="2df1f-111">特性</span><span class="sxs-lookup"><span data-stu-id="2df1f-111">Attribute</span></span>|<span data-ttu-id="2df1f-112">描述</span><span class="sxs-lookup"><span data-stu-id="2df1f-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="2df1f-113">id</span><span class="sxs-lookup"><span data-stu-id="2df1f-113">id</span></span>|<span data-ttu-id="2df1f-114">一个必需的属性，包含一个指定持久类型唯一标识符的字符串。</span><span class="sxs-lookup"><span data-stu-id="2df1f-114">A required attribute that contains a string that specifies a unique identifier for a persistable type.</span></span>|  
|<span data-ttu-id="2df1f-115">name</span><span class="sxs-lookup"><span data-stu-id="2df1f-115">name</span></span>|<span data-ttu-id="2df1f-116">一个可选属性，包含一个指定持久类型名称的字符串。</span><span class="sxs-lookup"><span data-stu-id="2df1f-116">An optional attribute that contains a string that specifies the name of the persistable type.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="2df1f-117">子元素</span><span class="sxs-lookup"><span data-stu-id="2df1f-117">Child Elements</span></span>  
 <span data-ttu-id="2df1f-118">None</span><span class="sxs-lookup"><span data-stu-id="2df1f-118">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="2df1f-119">父元素</span><span class="sxs-lookup"><span data-stu-id="2df1f-119">Parent Elements</span></span>  
  
|<span data-ttu-id="2df1f-120">元素</span><span class="sxs-lookup"><span data-stu-id="2df1f-120">Element</span></span>|<span data-ttu-id="2df1f-121">描述</span><span class="sxs-lookup"><span data-stu-id="2df1f-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2df1f-122">\<persistableTypes></span><span class="sxs-lookup"><span data-stu-id="2df1f-122">\<persistableTypes></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/persistabletypes.md)|<span data-ttu-id="2df1f-123">一个 `persistableType` 元素集合。</span><span class="sxs-lookup"><span data-stu-id="2df1f-123">A collection of `persistableType` elements.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="2df1f-124">请参阅</span><span class="sxs-lookup"><span data-stu-id="2df1f-124">See also</span></span>

- <xref:System.ServiceModel.Configuration.ComPersistableTypeElementCollection>
- <xref:System.ServiceModel.Configuration.ComPersistableTypeElement>
- [<span data-ttu-id="2df1f-125">\<comContracts></span><span class="sxs-lookup"><span data-stu-id="2df1f-125">\<comContracts></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/comcontracts.md)
- [<span data-ttu-id="2df1f-126">与 COM+ 应用程序集成</span><span class="sxs-lookup"><span data-stu-id="2df1f-126">Integrating with COM+ Applications</span></span>](../../../../../docs/framework/wcf/feature-details/integrating-with-com-plus-applications.md)
- [<span data-ttu-id="2df1f-127">如何：配置 COM + 服务设置</span><span class="sxs-lookup"><span data-stu-id="2df1f-127">How to: Configure COM+ Service Settings</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-configure-com-service-settings.md)
