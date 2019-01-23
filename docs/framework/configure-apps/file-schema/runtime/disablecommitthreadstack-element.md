---
title: '&lt;disableCommitThreadStack&gt;元素'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/disableCommitThreadStack
- http://schemas.microsoft.com/.NetConfiguration/v2.0#disableCommitThreadStack
helpviewer_keywords:
- <disableCommitThreadStack> element
- disableCommitThreadStack element
ms.assetid: 3559d46a-7640-4c72-9a11-7e980768929e
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3b02a5365aa2dc2292b0917820782405ba35ad92
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54534064"
---
# <a name="ltdisablecommitthreadstackgt-element"></a><span data-ttu-id="c89d1-102">&lt;disableCommitThreadStack&gt;元素</span><span class="sxs-lookup"><span data-stu-id="c89d1-102">&lt;disableCommitThreadStack&gt; Element</span></span>
<span data-ttu-id="c89d1-103">指定在线程启动时是否提交完整线程堆栈。</span><span class="sxs-lookup"><span data-stu-id="c89d1-103">Specifies whether the full thread stack is committed when a thread is started.</span></span>  
  
 <span data-ttu-id="c89d1-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="c89d1-104">\<configuration></span></span>  
<span data-ttu-id="c89d1-105">\<运行时 ></span><span class="sxs-lookup"><span data-stu-id="c89d1-105">\<runtime></span></span>  
<span data-ttu-id="c89d1-106">\<disableCommitThreadStack></span><span class="sxs-lookup"><span data-stu-id="c89d1-106">\<disableCommitThreadStack></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c89d1-107">语法</span><span class="sxs-lookup"><span data-stu-id="c89d1-107">Syntax</span></span>  
  
```xml  
<disableCommitThreadStack enabled="0|1"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c89d1-108">特性和元素</span><span class="sxs-lookup"><span data-stu-id="c89d1-108">Attributes and Elements</span></span>  
 <span data-ttu-id="c89d1-109">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="c89d1-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c89d1-110">特性</span><span class="sxs-lookup"><span data-stu-id="c89d1-110">Attributes</span></span>  
  
|<span data-ttu-id="c89d1-111">特性</span><span class="sxs-lookup"><span data-stu-id="c89d1-111">Attribute</span></span>|<span data-ttu-id="c89d1-112">描述</span><span class="sxs-lookup"><span data-stu-id="c89d1-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="c89d1-113">enabled</span><span class="sxs-lookup"><span data-stu-id="c89d1-113">enabled</span></span>|<span data-ttu-id="c89d1-114">必需的特性。</span><span class="sxs-lookup"><span data-stu-id="c89d1-114">Required attribute.</span></span><br /><br /> <span data-ttu-id="c89d1-115">指定是否禁止在线程启动时提交完整线程堆栈（默认行为）。</span><span class="sxs-lookup"><span data-stu-id="c89d1-115">Specifies whether committing the full thread stack on thread startup (the default behavior) is disabled.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="c89d1-116">enabled 特性</span><span class="sxs-lookup"><span data-stu-id="c89d1-116">enabled Attribute</span></span>  
  
|<span data-ttu-id="c89d1-117">值</span><span class="sxs-lookup"><span data-stu-id="c89d1-117">Value</span></span>|<span data-ttu-id="c89d1-118">描述</span><span class="sxs-lookup"><span data-stu-id="c89d1-118">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="c89d1-119">0</span><span class="sxs-lookup"><span data-stu-id="c89d1-119">0</span></span>|<span data-ttu-id="c89d1-120">不禁用公共语言运行时的默认行为（即在线程启动时提交完整线程堆栈）。</span><span class="sxs-lookup"><span data-stu-id="c89d1-120">Do not disable the default behavior of the common language runtime, which is to commit the full thread stack when a thread is started.</span></span>|  
|<span data-ttu-id="c89d1-121">1</span><span class="sxs-lookup"><span data-stu-id="c89d1-121">1</span></span>|<span data-ttu-id="c89d1-122">禁用公共语言运行时的默认行为（即在线程启动时提交完整线程堆栈）。</span><span class="sxs-lookup"><span data-stu-id="c89d1-122">Disable the default behavior of the common language runtime, which is to commit the full thread stack when a thread is started.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c89d1-123">子元素</span><span class="sxs-lookup"><span data-stu-id="c89d1-123">Child Elements</span></span>  
 <span data-ttu-id="c89d1-124">无。</span><span class="sxs-lookup"><span data-stu-id="c89d1-124">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="c89d1-125">父元素</span><span class="sxs-lookup"><span data-stu-id="c89d1-125">Parent Elements</span></span>  
  
|<span data-ttu-id="c89d1-126">元素</span><span class="sxs-lookup"><span data-stu-id="c89d1-126">Element</span></span>|<span data-ttu-id="c89d1-127">描述</span><span class="sxs-lookup"><span data-stu-id="c89d1-127">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="c89d1-128">公共语言运行时和 [!INCLUDE[dnprdnshort](../../../../../includes/dnprdnshort-md.md)] 应用程序所使用的每个配置文件中的根元素。</span><span class="sxs-lookup"><span data-stu-id="c89d1-128">The root element in every configuration file used by the common language runtime and [!INCLUDE[dnprdnshort](../../../../../includes/dnprdnshort-md.md)] applications.</span></span>|  
|`runtime`|<span data-ttu-id="c89d1-129">包含有关程序集绑定和垃圾回收的信息。</span><span class="sxs-lookup"><span data-stu-id="c89d1-129">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c89d1-130">备注</span><span class="sxs-lookup"><span data-stu-id="c89d1-130">Remarks</span></span>  
 <span data-ttu-id="c89d1-131">公共语言运行时的默认行为是在线程启动时提交完整线程堆栈。</span><span class="sxs-lookup"><span data-stu-id="c89d1-131">The default behavior of the common language runtime is to commit the full thread stack when a thread is started.</span></span> <span data-ttu-id="c89d1-132">当必须在内存有限的服务器上创建大量线程，并且其中大多数线程都使用非常小的堆栈空间时，如果公共语言运行时在线程启动时不立即提交完整线程堆栈，则服务器可能会表现更好。</span><span class="sxs-lookup"><span data-stu-id="c89d1-132">If a large number of threads must be created on a server that has limited memory, and most of those threads will use very little stack space, the server might perform better if the common language runtime does not commit the full thread stack immediately when a thread is started.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c89d1-133">非托管主机可以使用 `STARTUP_DISABLE_COMMITTHREADSTACK` STARTUP_FLAGS [枚举中的](../../../../../docs/framework/unmanaged-api/hosting/startup-flags-enumeration.md) 启动标志实现相同结果。</span><span class="sxs-lookup"><span data-stu-id="c89d1-133">Unmanaged hosts can use the `STARTUP_DISABLE_COMMITTHREADSTACK` startup flag in the [STARTUP_FLAGS](../../../../../docs/framework/unmanaged-api/hosting/startup-flags-enumeration.md) enumeration to accomplish the same result.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c89d1-134">示例</span><span class="sxs-lookup"><span data-stu-id="c89d1-134">Example</span></span>  
 <span data-ttu-id="c89d1-135">下面的示例演示如何禁用公共语言运行时的默认行为（即在线程启动时提交完整线程堆栈）。</span><span class="sxs-lookup"><span data-stu-id="c89d1-135">The following example shows how to disable the default behavior of the common language runtime, which is to commit the full thread stack on thread startup.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <disableCommitThreadStack enabled="1" />  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="c89d1-136">请参阅</span><span class="sxs-lookup"><span data-stu-id="c89d1-136">See also</span></span>
- [<span data-ttu-id="c89d1-137">运行时设置架构</span><span class="sxs-lookup"><span data-stu-id="c89d1-137">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)
- [<span data-ttu-id="c89d1-138">配置文件架构</span><span class="sxs-lookup"><span data-stu-id="c89d1-138">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)
