---
title: <persistableType>
ms.date: 03/30/2017
ms.assetid: e5425fe6-523a-4076-aab4-2c2515b1d830
ms.openlocfilehash: 328caaefe0cc24da45b460cab0a672dc8a6ccce1
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/10/2019
ms.locfileid: "70855068"
---
# <a name="persistabletype"></a><span data-ttu-id="620a0-101">\<persistableType></span><span class="sxs-lookup"><span data-stu-id="620a0-101">\<persistableType></span></span>
<span data-ttu-id="620a0-102">指定所有永久类型。</span><span class="sxs-lookup"><span data-stu-id="620a0-102">Specifies all the persistable types.</span></span>  
  
<span data-ttu-id="620a0-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="620a0-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="620a0-104">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="620a0-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="620a0-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<comContracts >** ](comcontracts.md)</span><span class="sxs-lookup"><span data-stu-id="620a0-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<comContracts>**](comcontracts.md)</span></span>\
<span data-ttu-id="620a0-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<comContract >** ](comcontract.md)</span><span class="sxs-lookup"><span data-stu-id="620a0-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<comContract>**](comcontract.md)</span></span>\
<span data-ttu-id="620a0-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<persistableTypes >** ](persistabletypes.md)</span><span class="sxs-lookup"><span data-stu-id="620a0-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<persistableTypes>**](persistabletypes.md)</span></span>\
<span data-ttu-id="620a0-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<persistableType >**</span><span class="sxs-lookup"><span data-stu-id="620a0-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<persistableType>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="620a0-109">语法</span><span class="sxs-lookup"><span data-stu-id="620a0-109">Syntax</span></span>  
  
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
  
## <a name="type"></a><span data-ttu-id="620a0-110">类型</span><span class="sxs-lookup"><span data-stu-id="620a0-110">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="620a0-111">特性和元素</span><span class="sxs-lookup"><span data-stu-id="620a0-111">Attributes and Elements</span></span>  
 <span data-ttu-id="620a0-112">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="620a0-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="620a0-113">特性</span><span class="sxs-lookup"><span data-stu-id="620a0-113">Attributes</span></span>  
  
|<span data-ttu-id="620a0-114">特性</span><span class="sxs-lookup"><span data-stu-id="620a0-114">Attribute</span></span>|<span data-ttu-id="620a0-115">描述</span><span class="sxs-lookup"><span data-stu-id="620a0-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="620a0-116">id</span><span class="sxs-lookup"><span data-stu-id="620a0-116">id</span></span>|<span data-ttu-id="620a0-117">一个必需的属性，包含一个指定持久类型唯一标识符的字符串。</span><span class="sxs-lookup"><span data-stu-id="620a0-117">A required attribute that contains a string that specifies a unique identifier for a persistable type.</span></span>|  
|<span data-ttu-id="620a0-118">NAME</span><span class="sxs-lookup"><span data-stu-id="620a0-118">name</span></span>|<span data-ttu-id="620a0-119">一个可选属性，包含一个指定持久类型名称的字符串。</span><span class="sxs-lookup"><span data-stu-id="620a0-119">An optional attribute that contains a string that specifies the name of the persistable type.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="620a0-120">子元素</span><span class="sxs-lookup"><span data-stu-id="620a0-120">Child Elements</span></span>  
 <span data-ttu-id="620a0-121">无</span><span class="sxs-lookup"><span data-stu-id="620a0-121">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="620a0-122">父元素</span><span class="sxs-lookup"><span data-stu-id="620a0-122">Parent Elements</span></span>  
  
|<span data-ttu-id="620a0-123">元素</span><span class="sxs-lookup"><span data-stu-id="620a0-123">Element</span></span>|<span data-ttu-id="620a0-124">描述</span><span class="sxs-lookup"><span data-stu-id="620a0-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="620a0-125">\<persistableTypes></span><span class="sxs-lookup"><span data-stu-id="620a0-125">\<persistableTypes></span></span>](persistabletypes.md)|<span data-ttu-id="620a0-126">一个 `persistableType` 元素集合。</span><span class="sxs-lookup"><span data-stu-id="620a0-126">A collection of `persistableType` elements.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="620a0-127">请参阅</span><span class="sxs-lookup"><span data-stu-id="620a0-127">See also</span></span>

- <xref:System.ServiceModel.Configuration.ComPersistableTypeElementCollection>
- <xref:System.ServiceModel.Configuration.ComPersistableTypeElement>
- [<span data-ttu-id="620a0-128">\<comContracts></span><span class="sxs-lookup"><span data-stu-id="620a0-128">\<comContracts></span></span>](comcontracts.md)
- [<span data-ttu-id="620a0-129">与 COM+ 应用程序集成</span><span class="sxs-lookup"><span data-stu-id="620a0-129">Integrating with COM+ Applications</span></span>](../../../wcf/feature-details/integrating-with-com-plus-applications.md)
- [<span data-ttu-id="620a0-130">如何：配置 COM + 服务设置</span><span class="sxs-lookup"><span data-stu-id="620a0-130">How to: Configure COM+ Service Settings</span></span>](../../../wcf/feature-details/how-to-configure-com-service-settings.md)
