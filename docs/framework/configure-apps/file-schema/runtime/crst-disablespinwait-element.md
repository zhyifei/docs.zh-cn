---
title: < Crst_DisableSpinWait > 元素
ms.date: 04/18/2019
f1_keywords:
- Crst_DisableSpinWait
helpviewer_keywords:
- Crst_DisableSpinWait element
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6cde26250db0b3d11c51a18b7ebd378953ae0958
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61704825"
---
# <a name="crstdisablespinwait-element"></a><span data-ttu-id="21a0f-102">\<Crst_DisableSpinWait > 元素</span><span class="sxs-lookup"><span data-stu-id="21a0f-102">\<Crst_DisableSpinWait> element</span></span>

<span data-ttu-id="21a0f-103">指定是否禁用数值调节钮等待关键部分时争用。</span><span class="sxs-lookup"><span data-stu-id="21a0f-103">Specifies whether to disable spin-waiting for a critical section when contended.</span></span> \ 
  
 <span data-ttu-id="21a0f-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="21a0f-104">\<configuration></span></span>  
<span data-ttu-id="21a0f-105">\<运行时 ></span><span class="sxs-lookup"><span data-stu-id="21a0f-105">\<runtime></span></span>  
<span data-ttu-id="21a0f-106">\<Crst_DisableSpinWait></span><span class="sxs-lookup"><span data-stu-id="21a0f-106">\<Crst_DisableSpinWait></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="21a0f-107">语法</span><span class="sxs-lookup"><span data-stu-id="21a0f-107">Syntax</span></span>  
  
```xml  
<Crst_DisableSpinWait enabled="true | false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="21a0f-108">特性和元素</span><span class="sxs-lookup"><span data-stu-id="21a0f-108">Attributes and Elements</span></span>

<span data-ttu-id="21a0f-109">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="21a0f-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="21a0f-110">特性</span><span class="sxs-lookup"><span data-stu-id="21a0f-110">Attributes</span></span>  
  
|<span data-ttu-id="21a0f-111">特性</span><span class="sxs-lookup"><span data-stu-id="21a0f-111">Attribute</span></span>|<span data-ttu-id="21a0f-112">描述</span><span class="sxs-lookup"><span data-stu-id="21a0f-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="21a0f-113">**enabled**</span><span class="sxs-lookup"><span data-stu-id="21a0f-113">**enabled**</span></span>|<span data-ttu-id="21a0f-114">指定当它们争用时是否启用数值调节钮等待关键部分。</span><span class="sxs-lookup"><span data-stu-id="21a0f-114">Specifies whether spin-waiting for critical sections is enabled when they are contended.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="21a0f-115">enabled 特性</span><span class="sxs-lookup"><span data-stu-id="21a0f-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="21a0f-116">“值”</span><span class="sxs-lookup"><span data-stu-id="21a0f-116">Value</span></span>|<span data-ttu-id="21a0f-117">描述</span><span class="sxs-lookup"><span data-stu-id="21a0f-117">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="21a0f-118">1</span><span class="sxs-lookup"><span data-stu-id="21a0f-118">1</span></span>|<span data-ttu-id="21a0f-119">数值调节钮等待已启用。</span><span class="sxs-lookup"><span data-stu-id="21a0f-119">Spin-waiting is enabled.</span></span>|  
|<span data-ttu-id="21a0f-120">0</span><span class="sxs-lookup"><span data-stu-id="21a0f-120">0</span></span>|<span data-ttu-id="21a0f-121">数值调节钮等待处于禁用状态。</span><span class="sxs-lookup"><span data-stu-id="21a0f-121">Spin-waiting is disabled.</span></span> <span data-ttu-id="21a0f-122">这是默认值</span><span class="sxs-lookup"><span data-stu-id="21a0f-122">This is the default</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="21a0f-123">子元素</span><span class="sxs-lookup"><span data-stu-id="21a0f-123">Child Elements</span></span>  
 <span data-ttu-id="21a0f-124">无。</span><span class="sxs-lookup"><span data-stu-id="21a0f-124">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="21a0f-125">父元素</span><span class="sxs-lookup"><span data-stu-id="21a0f-125">Parent Elements</span></span>  
  
|<span data-ttu-id="21a0f-126">元素</span><span class="sxs-lookup"><span data-stu-id="21a0f-126">Element</span></span>|<span data-ttu-id="21a0f-127">描述</span><span class="sxs-lookup"><span data-stu-id="21a0f-127">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="21a0f-128">公共语言运行时和 .NET Framework 应用程序所使用的每个配置文件中的根元素。</span><span class="sxs-lookup"><span data-stu-id="21a0f-128">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="21a0f-129">包含有关运行时的各种配置设置的信息。</span><span class="sxs-lookup"><span data-stu-id="21a0f-129">Contains information about various runtime configuration settings.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="21a0f-130">示例</span><span class="sxs-lookup"><span data-stu-id="21a0f-130">Example</span></span>  

<span data-ttu-id="21a0f-131">以下示例禁用数值调节钮-等待在临界区时争用。</span><span class="sxs-lookup"><span data-stu-id="21a0f-131">The following example disables spin-waiting in critical sections when contended.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <Crst_DisableSpinWait enabled="1"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="21a0f-132">请参阅</span><span class="sxs-lookup"><span data-stu-id="21a0f-132">See also</span></span>

- [<span data-ttu-id="21a0f-133">运行时设置架构</span><span class="sxs-lookup"><span data-stu-id="21a0f-133">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)
- [<span data-ttu-id="21a0f-134">配置文件架构</span><span class="sxs-lookup"><span data-stu-id="21a0f-134">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)
