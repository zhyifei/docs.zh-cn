---
title: "分析结构"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
helpviewer_keywords:
- profiling structures [.NET Framework]
- unmanaged structures [.NET Framework], profiling
- structures [.NET Framework profiling]
ms.assetid: 750385f2-f365-41b1-939f-ca2f2ff9b466
caps.latest.revision: "27"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: b29c63ea9dfbd69863aad1afa712444405be763e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="profiling-structures"></a><span data-ttu-id="5e19f-102">分析结构</span><span class="sxs-lookup"><span data-stu-id="5e19f-102">Profiling Structures</span></span>
<span data-ttu-id="5e19f-103">本节描述分析 API 使用的非托管结构。</span><span class="sxs-lookup"><span data-stu-id="5e19f-103">This section describes the unmanaged structures that the profiling API uses.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="5e19f-104">本节内容</span><span class="sxs-lookup"><span data-stu-id="5e19f-104">In This Section</span></span>  
 [<span data-ttu-id="5e19f-105">COR_PRF_ASSEMBLY_REFERENCE_INFO 结构</span><span class="sxs-lookup"><span data-stu-id="5e19f-105">COR_PRF_ASSEMBLY_REFERENCE_INFO Structure</span></span>](../../../../docs/framework/unmanaged-api/profiling/cor-prf-assembly-reference-info-structure.md)  
 <span data-ttu-id="5e19f-106">向公共语言运行时提供有关在执行程序集引用闭包审核时应考虑的引用程序集的信息。</span><span class="sxs-lookup"><span data-stu-id="5e19f-106">Provides the common language runtime with information about a reference assembly that it should consider when performing an assembly reference closure walk.</span></span>  
  
 [<span data-ttu-id="5e19f-107">COR_PRF_CODE_INFO 结构</span><span class="sxs-lookup"><span data-stu-id="5e19f-107">COR_PRF_CODE_INFO Structure</span></span>](../../../../docs/framework/unmanaged-api/profiling/cor-prf-code-info-structure.md)  
 <span data-ttu-id="5e19f-108">表示存储在内存中的一个本机代码连续块。</span><span class="sxs-lookup"><span data-stu-id="5e19f-108">Represents one contiguous block of native code stored in memory.</span></span>  
  
 [<span data-ttu-id="5e19f-109">COR_PRF_EX_CLAUSE_INFO 结构</span><span class="sxs-lookup"><span data-stu-id="5e19f-109">COR_PRF_EX_CLAUSE_INFO Structure</span></span>](../../../../docs/framework/unmanaged-api/profiling/cor-prf-ex-clause-info-structure.md)  
 <span data-ttu-id="5e19f-110">存储有关特定的异常子句实例及其关联的帧的信息。</span><span class="sxs-lookup"><span data-stu-id="5e19f-110">Stores information about a specific exception clause instance and its associated frame.</span></span>  
  
 [<span data-ttu-id="5e19f-111">COR_PRF_FUNCTION 结构</span><span class="sxs-lookup"><span data-stu-id="5e19f-111">COR_PRF_FUNCTION Structure</span></span>](../../../../docs/framework/unmanaged-api/profiling/cor-prf-function-structure.md)  
 <span data-ttu-id="5e19f-112">通过将函数的 ID 与其重新编译的 ID 版本组合起来，提供该函数的唯一表示形式。</span><span class="sxs-lookup"><span data-stu-id="5e19f-112">Provides a unique representation of a function by combining its ID with the ID of its recompiled version.</span></span>  
  
 [<span data-ttu-id="5e19f-113">COR_PRF_FUNCTION_ARGUMENT_INFO 结构</span><span class="sxs-lookup"><span data-stu-id="5e19f-113">COR_PRF_FUNCTION_ARGUMENT_INFO Structure</span></span>](../../../../docs/framework/unmanaged-api/profiling/cor-prf-function-argument-info-structure.md)  
 <span data-ttu-id="5e19f-114">按从左向右的顺序表示函数的自变量。</span><span class="sxs-lookup"><span data-stu-id="5e19f-114">Represents a function's arguments, in left-to-right order.</span></span>  
  
 [<span data-ttu-id="5e19f-115">COR_PRF_FUNCTION_ARGUMENT_RANGE 结构</span><span class="sxs-lookup"><span data-stu-id="5e19f-115">COR_PRF_FUNCTION_ARGUMENT_RANGE Structure</span></span>](../../../../docs/framework/unmanaged-api/profiling/cor-prf-function-argument-range-structure.md)  
 <span data-ttu-id="5e19f-116">表示内存中按从左向右的顺序连续存储的函数自变量块。</span><span class="sxs-lookup"><span data-stu-id="5e19f-116">Represents a block of function arguments stored contiguously in left-to-right order in memory.</span></span>  
  
 [<span data-ttu-id="5e19f-117">COR_PRF_GC_GENERATION_RANGE 结构</span><span class="sxs-lookup"><span data-stu-id="5e19f-117">COR_PRF_GC_GENERATION_RANGE Structure</span></span>](../../../../docs/framework/unmanaged-api/profiling/cor-prf-gc-generation-range-structure.md)  
 <span data-ttu-id="5e19f-118">描述一个正进行垃圾回收的内存范围（即块）。</span><span class="sxs-lookup"><span data-stu-id="5e19f-118">Describes a range (that is, block) of memory that is undergoing garbage collection.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="5e19f-119">相关章节</span><span class="sxs-lookup"><span data-stu-id="5e19f-119">Related Sections</span></span>  
 <span data-ttu-id="5e19f-120">COR_DEBUG_IL_TO_NATIVE_MAP</span><span class="sxs-lookup"><span data-stu-id="5e19f-120">COR_DEBUG_IL_TO_NATIVE_MAP</span></span>  
  
 <span data-ttu-id="5e19f-121">COR_IL_MAP</span><span class="sxs-lookup"><span data-stu-id="5e19f-121">COR_IL_MAP</span></span>  
  
 [<span data-ttu-id="5e19f-122">分析概述</span><span class="sxs-lookup"><span data-stu-id="5e19f-122">Profiling Overview</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-overview.md)  
  
 [<span data-ttu-id="5e19f-123">Profiling 接口</span><span class="sxs-lookup"><span data-stu-id="5e19f-123">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)  
  
 [<span data-ttu-id="5e19f-124">分析全局静态函数</span><span class="sxs-lookup"><span data-stu-id="5e19f-124">Profiling Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-global-static-functions.md)  
  
 [<span data-ttu-id="5e19f-125">分析枚举</span><span class="sxs-lookup"><span data-stu-id="5e19f-125">Profiling Enumerations</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)
