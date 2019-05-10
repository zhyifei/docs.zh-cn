---
title: < Crst_DisableSpinWait > 元素
ms.date: 04/18/2019
f1_keywords:
- Crst_DisableSpinWait
helpviewer_keywords:
- Crst_DisableSpinWait element
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f89f0558c11e229fef2ca3cd619e3c033f12c858
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "64754672"
---
# <a name="crstdisablespinwait-element"></a><span data-ttu-id="b19fd-102">\<Crst_DisableSpinWait > 元素</span><span class="sxs-lookup"><span data-stu-id="b19fd-102">\<Crst_DisableSpinWait> element</span></span>

<span data-ttu-id="b19fd-103">指定是否禁用数值调节钮等待关键部分时争用。</span><span class="sxs-lookup"><span data-stu-id="b19fd-103">Specifies whether to disable spin-waiting for a critical section when contended.</span></span>  
  
 <span data-ttu-id="b19fd-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="b19fd-104">\<configuration></span></span>  
<span data-ttu-id="b19fd-105">\<运行时 ></span><span class="sxs-lookup"><span data-stu-id="b19fd-105">\<runtime></span></span>  
<span data-ttu-id="b19fd-106">\<Crst_DisableSpinWait></span><span class="sxs-lookup"><span data-stu-id="b19fd-106">\<Crst_DisableSpinWait></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b19fd-107">语法</span><span class="sxs-lookup"><span data-stu-id="b19fd-107">Syntax</span></span>  
  
```xml  
<Crst_DisableSpinWait enabled="true | false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b19fd-108">特性和元素</span><span class="sxs-lookup"><span data-stu-id="b19fd-108">Attributes and Elements</span></span>

<span data-ttu-id="b19fd-109">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="b19fd-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b19fd-110">特性</span><span class="sxs-lookup"><span data-stu-id="b19fd-110">Attributes</span></span>  
  
|<span data-ttu-id="b19fd-111">特性</span><span class="sxs-lookup"><span data-stu-id="b19fd-111">Attribute</span></span>|<span data-ttu-id="b19fd-112">描述</span><span class="sxs-lookup"><span data-stu-id="b19fd-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="b19fd-113">**enabled**</span><span class="sxs-lookup"><span data-stu-id="b19fd-113">**enabled**</span></span>|<span data-ttu-id="b19fd-114">指定是否禁用数值调节钮等待关键节时它们激烈。</span><span class="sxs-lookup"><span data-stu-id="b19fd-114">Specifies whether spin-waiting for critical sections when they are contended is disabled.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="b19fd-115">enabled 特性</span><span class="sxs-lookup"><span data-stu-id="b19fd-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="b19fd-116">值</span><span class="sxs-lookup"><span data-stu-id="b19fd-116">Value</span></span>|<span data-ttu-id="b19fd-117">描述</span><span class="sxs-lookup"><span data-stu-id="b19fd-117">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="b19fd-118">1</span><span class="sxs-lookup"><span data-stu-id="b19fd-118">1</span></span>|<span data-ttu-id="b19fd-119">不能获取关键节时，可禁用数值调节钮等待。</span><span class="sxs-lookup"><span data-stu-id="b19fd-119">Disable spin-waiting when a critical section cannot be acquired.</span></span>|  
|<span data-ttu-id="b19fd-120">0</span><span class="sxs-lookup"><span data-stu-id="b19fd-120">0</span></span>|<span data-ttu-id="b19fd-121">不能获取关键节时，请勿禁用旋转等待。</span><span class="sxs-lookup"><span data-stu-id="b19fd-121">Do not disable spin-waiting when a critical section cannot be acquired.</span></span> <span data-ttu-id="b19fd-122">这是默认值。</span><span class="sxs-lookup"><span data-stu-id="b19fd-122">This is the default value.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b19fd-123">子元素</span><span class="sxs-lookup"><span data-stu-id="b19fd-123">Child Elements</span></span>  
 <span data-ttu-id="b19fd-124">无。</span><span class="sxs-lookup"><span data-stu-id="b19fd-124">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="b19fd-125">父元素</span><span class="sxs-lookup"><span data-stu-id="b19fd-125">Parent Elements</span></span>  
  
|<span data-ttu-id="b19fd-126">元素</span><span class="sxs-lookup"><span data-stu-id="b19fd-126">Element</span></span>|<span data-ttu-id="b19fd-127">描述</span><span class="sxs-lookup"><span data-stu-id="b19fd-127">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="b19fd-128">公共语言运行时和 .NET Framework 应用程序所使用的每个配置文件中的根元素。</span><span class="sxs-lookup"><span data-stu-id="b19fd-128">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="b19fd-129">包含有关运行时的各种配置设置的信息。</span><span class="sxs-lookup"><span data-stu-id="b19fd-129">Contains information about various runtime configuration settings.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="b19fd-130">示例</span><span class="sxs-lookup"><span data-stu-id="b19fd-130">Example</span></span>  

<span data-ttu-id="b19fd-131">以下示例禁用数值调节钮-等待在临界区时争用。</span><span class="sxs-lookup"><span data-stu-id="b19fd-131">The following example disables spin-waiting in critical sections when contended.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <Crst_DisableSpinWait enabled="1"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="b19fd-132">请参阅</span><span class="sxs-lookup"><span data-stu-id="b19fd-132">See also</span></span>

- [<span data-ttu-id="b19fd-133">运行时设置架构</span><span class="sxs-lookup"><span data-stu-id="b19fd-133">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)
- [<span data-ttu-id="b19fd-134">配置文件架构</span><span class="sxs-lookup"><span data-stu-id="b19fd-134">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)
