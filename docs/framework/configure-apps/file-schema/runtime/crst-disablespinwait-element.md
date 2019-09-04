---
title: < Crst_DisableSpinWait > 元素
ms.date: 04/18/2019
f1_keywords:
- Crst_DisableSpinWait
helpviewer_keywords:
- Crst_DisableSpinWait element
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 8a91e21120ecebbe7af2fb93798bc68d274fa92c
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/04/2019
ms.locfileid: "70252716"
---
# <a name="crst_disablespinwait-element"></a><span data-ttu-id="24a82-102">\<Crst_DisableSpinWait > 元素</span><span class="sxs-lookup"><span data-stu-id="24a82-102">\<Crst_DisableSpinWait> element</span></span>

<span data-ttu-id="24a82-103">指定是否在争用时禁用临界区等待。</span><span class="sxs-lookup"><span data-stu-id="24a82-103">Specifies whether to disable spin-waiting for a critical section when contended.</span></span>  
  
<span data-ttu-id="24a82-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="24a82-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="24a82-105">&nbsp;&nbsp;[ **\<运行时 >** ](runtime-element.md)</span><span class="sxs-lookup"><span data-stu-id="24a82-105">&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)</span></span>\
<span data-ttu-id="24a82-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<Crst_DisableSpinWait >**</span><span class="sxs-lookup"><span data-stu-id="24a82-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<Crst_DisableSpinWait>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="24a82-107">语法</span><span class="sxs-lookup"><span data-stu-id="24a82-107">Syntax</span></span>  
  
```xml  
<Crst_DisableSpinWait enabled="true | false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="24a82-108">特性和元素</span><span class="sxs-lookup"><span data-stu-id="24a82-108">Attributes and Elements</span></span>

<span data-ttu-id="24a82-109">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="24a82-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="24a82-110">特性</span><span class="sxs-lookup"><span data-stu-id="24a82-110">Attributes</span></span>  
  
|<span data-ttu-id="24a82-111">特性</span><span class="sxs-lookup"><span data-stu-id="24a82-111">Attribute</span></span>|<span data-ttu-id="24a82-112">描述</span><span class="sxs-lookup"><span data-stu-id="24a82-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="24a82-113">**enabled**</span><span class="sxs-lookup"><span data-stu-id="24a82-113">**enabled**</span></span>|<span data-ttu-id="24a82-114">指定禁用已争用的关键部分时，是否旋转等待。</span><span class="sxs-lookup"><span data-stu-id="24a82-114">Specifies whether spin-waiting for critical sections when they are contended is disabled.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="24a82-115">enabled 特性</span><span class="sxs-lookup"><span data-stu-id="24a82-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="24a82-116">值</span><span class="sxs-lookup"><span data-stu-id="24a82-116">Value</span></span>|<span data-ttu-id="24a82-117">描述</span><span class="sxs-lookup"><span data-stu-id="24a82-117">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="24a82-118">1</span><span class="sxs-lookup"><span data-stu-id="24a82-118">1</span></span>|<span data-ttu-id="24a82-119">禁用在无法获取关键部分时等待自旋。</span><span class="sxs-lookup"><span data-stu-id="24a82-119">Disable spin-waiting when a critical section cannot be acquired.</span></span>|  
|<span data-ttu-id="24a82-120">0</span><span class="sxs-lookup"><span data-stu-id="24a82-120">0</span></span>|<span data-ttu-id="24a82-121">不要在无法获取关键节时禁用自旋等待。</span><span class="sxs-lookup"><span data-stu-id="24a82-121">Do not disable spin-waiting when a critical section cannot be acquired.</span></span> <span data-ttu-id="24a82-122">这是默认值。</span><span class="sxs-lookup"><span data-stu-id="24a82-122">This is the default value.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="24a82-123">子元素</span><span class="sxs-lookup"><span data-stu-id="24a82-123">Child Elements</span></span>  
 <span data-ttu-id="24a82-124">无。</span><span class="sxs-lookup"><span data-stu-id="24a82-124">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="24a82-125">父元素</span><span class="sxs-lookup"><span data-stu-id="24a82-125">Parent Elements</span></span>  
  
|<span data-ttu-id="24a82-126">元素</span><span class="sxs-lookup"><span data-stu-id="24a82-126">Element</span></span>|<span data-ttu-id="24a82-127">描述</span><span class="sxs-lookup"><span data-stu-id="24a82-127">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="24a82-128">公共语言运行时和 .NET Framework 应用程序所使用的每个配置文件中的根元素。</span><span class="sxs-lookup"><span data-stu-id="24a82-128">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="24a82-129">包含有关各种运行时配置设置的信息。</span><span class="sxs-lookup"><span data-stu-id="24a82-129">Contains information about various runtime configuration settings.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="24a82-130">示例</span><span class="sxs-lookup"><span data-stu-id="24a82-130">Example</span></span>  

<span data-ttu-id="24a82-131">下面的示例在争用时在关键部分禁用自旋。</span><span class="sxs-lookup"><span data-stu-id="24a82-131">The following example disables spin-waiting in critical sections when contended.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <Crst_DisableSpinWait enabled="1"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="24a82-132">请参阅</span><span class="sxs-lookup"><span data-stu-id="24a82-132">See also</span></span>

- [<span data-ttu-id="24a82-133">运行时设置架构</span><span class="sxs-lookup"><span data-stu-id="24a82-133">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="24a82-134">配置文件架构</span><span class="sxs-lookup"><span data-stu-id="24a82-134">Configuration File Schema</span></span>](../index.md)
