---
title: "承载结构"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
helpviewer_keywords:
- hosting structures [.NET Framework]
- unmanaged structures [.NET Framework], hosting
- structures [.NET Framework hosting]
ms.assetid: 492e010f-7493-4134-9505-f7008ccdaae6
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 24f6d667399d788d12d368832ed4d8638d29a0f5
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="hosting-structures"></a><span data-ttu-id="008d1-102">承载结构</span><span class="sxs-lookup"><span data-stu-id="008d1-102">Hosting Structures</span></span>
<span data-ttu-id="008d1-103">本部分描述承载 API 使用的非托管的结构。</span><span class="sxs-lookup"><span data-stu-id="008d1-103">This section describes the unmanaged structures that the hosting API uses.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="008d1-104">本节内容</span><span class="sxs-lookup"><span data-stu-id="008d1-104">In This Section</span></span>  
 [<span data-ttu-id="008d1-105">AssemblyBindInfo 结构</span><span class="sxs-lookup"><span data-stu-id="008d1-105">AssemblyBindInfo Structure</span></span>](../../../../docs/framework/unmanaged-api/hosting/assemblybindinfo-structure.md)  
 <span data-ttu-id="008d1-106">提供有关引用程序集的详细的信息。</span><span class="sxs-lookup"><span data-stu-id="008d1-106">Provides detailed information about the referenced assembly.</span></span>  
  
 [<span data-ttu-id="008d1-107">BucketParameters 结构</span><span class="sxs-lookup"><span data-stu-id="008d1-107">BucketParameters Structure</span></span>](../../../../docs/framework/unmanaged-api/hosting/bucketparameters-structure.md)  
 <span data-ttu-id="008d1-108">将存储与事件相关联的当前异常的事件和参数的类型名称。</span><span class="sxs-lookup"><span data-stu-id="008d1-108">Stores the type name of an event and the parameters for the current exception that is associated with the event.</span></span>  
  
 [<span data-ttu-id="008d1-109">COR_GC_STATS 结构</span><span class="sxs-lookup"><span data-stu-id="008d1-109">COR_GC_STATS Structure</span></span>](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stats-structure.md)  
 <span data-ttu-id="008d1-110">提供有关垃圾回收机制的公共语言运行时 (CLR) 的统计信息。</span><span class="sxs-lookup"><span data-stu-id="008d1-110">Provides statistics about the garbage collection mechanism of the common language runtime (CLR).</span></span>  
  
 [<span data-ttu-id="008d1-111">COR_GC_THREAD_STATS 结构</span><span class="sxs-lookup"><span data-stu-id="008d1-111">COR_GC_THREAD_STATS Structure</span></span>](../../../../docs/framework/unmanaged-api/hosting/cor-gc-thread-stats-structure.md)  
 <span data-ttu-id="008d1-112">包含有关垃圾回收的每个线程统计信息。</span><span class="sxs-lookup"><span data-stu-id="008d1-112">Contains per-thread statistics pertaining to garbage collection.</span></span>  
  
 [<span data-ttu-id="008d1-113">CustomDumpItem 结构</span><span class="sxs-lookup"><span data-stu-id="008d1-113">CustomDumpItem Structure</span></span>](../../../../docs/framework/unmanaged-api/hosting/customdumpitem-structure.md)  
 <span data-ttu-id="008d1-114">描述要添加到自定义转储错误报告中的项。</span><span class="sxs-lookup"><span data-stu-id="008d1-114">Describes an item to be added to a custom dump in error reporting.</span></span>  
  
 [<span data-ttu-id="008d1-115">MDAInfo 结构</span><span class="sxs-lookup"><span data-stu-id="008d1-115">MDAInfo Structure</span></span>](../../../../docs/framework/unmanaged-api/hosting/mdainfo-structure.md)  
 <span data-ttu-id="008d1-116">提供有关的详细信息`Event_MDAFired`触发的托管调试助手 (MDA) 创建的事件。</span><span class="sxs-lookup"><span data-stu-id="008d1-116">Provides details about the `Event_MDAFired` event, which triggers the creation of a managed debugging assistant (MDA).</span></span>  
  
 [<span data-ttu-id="008d1-117">ModuleBindInfo 结构</span><span class="sxs-lookup"><span data-stu-id="008d1-117">ModuleBindInfo Structure</span></span>](../../../../docs/framework/unmanaged-api/hosting/modulebindinfo-structure.md)  
 <span data-ttu-id="008d1-118">提供有关引用的模块和包含它的程序集的详细的信息。</span><span class="sxs-lookup"><span data-stu-id="008d1-118">Provides detailed information about the referenced module and the assembly that contains it.</span></span>  
  
 [<span data-ttu-id="008d1-119">StackOverflowInfo 结构</span><span class="sxs-lookup"><span data-stu-id="008d1-119">StackOverflowInfo Structure</span></span>](../../../../docs/framework/unmanaged-api/hosting/stackoverflowinfo-structure.md)  
 <span data-ttu-id="008d1-120">由于溢出时引发的异常上存储的溢出发生和信息的类型。</span><span class="sxs-lookup"><span data-stu-id="008d1-120">Stores the type of overflow that occurred and information on the exception that was thrown due to the overflow.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="008d1-121">相关章节</span><span class="sxs-lookup"><span data-stu-id="008d1-121">Related Sections</span></span>  
 [<span data-ttu-id="008d1-122">承载组件类</span><span class="sxs-lookup"><span data-stu-id="008d1-122">Hosting Coclasses</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-coclasses.md)  
  
 [<span data-ttu-id="008d1-123">承载接口</span><span class="sxs-lookup"><span data-stu-id="008d1-123">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)  
  
 [<span data-ttu-id="008d1-124">弃用的 CLR 承载函数</span><span class="sxs-lookup"><span data-stu-id="008d1-124">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)  
  
 [<span data-ttu-id="008d1-125">承载枚举</span><span class="sxs-lookup"><span data-stu-id="008d1-125">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
