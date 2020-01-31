---
title: 分析结构
ms.date: 03/30/2017
helpviewer_keywords:
- profiling structures [.NET Framework]
- unmanaged structures [.NET Framework], profiling
- structures [.NET Framework profiling]
ms.assetid: 750385f2-f365-41b1-939f-ca2f2ff9b466
ms.openlocfilehash: c3bbc66079e05abf494ad112b8aa0ac68e3c3e2f
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/29/2020
ms.locfileid: "76868104"
---
# <a name="profiling-structures"></a><span data-ttu-id="8ca23-102">分析结构</span><span class="sxs-lookup"><span data-stu-id="8ca23-102">Profiling Structures</span></span>
<span data-ttu-id="8ca23-103">本节描述分析 API 使用的非托管结构。</span><span class="sxs-lookup"><span data-stu-id="8ca23-103">This section describes the unmanaged structures that the profiling API uses.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="8ca23-104">本节内容</span><span class="sxs-lookup"><span data-stu-id="8ca23-104">In This Section</span></span>  
 [<span data-ttu-id="8ca23-105">COR_PRF_ASSEMBLY_REFERENCE_INFO 结构</span><span class="sxs-lookup"><span data-stu-id="8ca23-105">COR_PRF_ASSEMBLY_REFERENCE_INFO Structure</span></span>](cor-prf-assembly-reference-info-structure.md)  
 <span data-ttu-id="8ca23-106">向公共语言运行时提供有关在执行程序集引用闭包审核时应考虑的引用程序集的信息。</span><span class="sxs-lookup"><span data-stu-id="8ca23-106">Provides the common language runtime with information about a reference assembly that it should consider when performing an assembly reference closure walk.</span></span>  
  
 [<span data-ttu-id="8ca23-107">COR_PRF_CODE_INFO 结构</span><span class="sxs-lookup"><span data-stu-id="8ca23-107">COR_PRF_CODE_INFO Structure</span></span>](cor-prf-code-info-structure.md)  
 <span data-ttu-id="8ca23-108">表示存储在内存中的一个本机代码连续块。</span><span class="sxs-lookup"><span data-stu-id="8ca23-108">Represents one contiguous block of native code stored in memory.</span></span>  
  
 [<span data-ttu-id="8ca23-109">COR_PRF_EX_CLAUSE_INFO 结构</span><span class="sxs-lookup"><span data-stu-id="8ca23-109">COR_PRF_EX_CLAUSE_INFO Structure</span></span>](cor-prf-ex-clause-info-structure.md)  
 <span data-ttu-id="8ca23-110">存储有关特定的异常子句实例及其关联的帧的信息。</span><span class="sxs-lookup"><span data-stu-id="8ca23-110">Stores information about a specific exception clause instance and its associated frame.</span></span>  
  
 [<span data-ttu-id="8ca23-111">COR_PRF_FUNCTION 结构</span><span class="sxs-lookup"><span data-stu-id="8ca23-111">COR_PRF_FUNCTION Structure</span></span>](cor-prf-function-structure.md)  
 <span data-ttu-id="8ca23-112">通过将函数的 ID 与其重新编译的 ID 版本组合起来，提供该函数的唯一表示形式。</span><span class="sxs-lookup"><span data-stu-id="8ca23-112">Provides a unique representation of a function by combining its ID with the ID of its recompiled version.</span></span>  
  
 [<span data-ttu-id="8ca23-113">COR_PRF_FUNCTION_ARGUMENT_INFO 结构</span><span class="sxs-lookup"><span data-stu-id="8ca23-113">COR_PRF_FUNCTION_ARGUMENT_INFO Structure</span></span>](cor-prf-function-argument-info-structure.md)  
 <span data-ttu-id="8ca23-114">按从左向右的顺序表示函数的参数。</span><span class="sxs-lookup"><span data-stu-id="8ca23-114">Represents a function's arguments, in left-to-right order.</span></span>  
  
 [<span data-ttu-id="8ca23-115">COR_PRF_FUNCTION_ARGUMENT_RANGE 结构</span><span class="sxs-lookup"><span data-stu-id="8ca23-115">COR_PRF_FUNCTION_ARGUMENT_RANGE Structure</span></span>](cor-prf-function-argument-range-structure.md)  
 <span data-ttu-id="8ca23-116">表示内存中按从左向右的顺序连续存储的函数自变量块。</span><span class="sxs-lookup"><span data-stu-id="8ca23-116">Represents a block of function arguments stored contiguously in left-to-right order in memory.</span></span>  
  
 [<span data-ttu-id="8ca23-117">COR_PRF_GC_GENERATION_RANGE 结构</span><span class="sxs-lookup"><span data-stu-id="8ca23-117">COR_PRF_GC_GENERATION_RANGE Structure</span></span>](cor-prf-gc-generation-range-structure.md)  
 <span data-ttu-id="8ca23-118">描述一个正进行垃圾回收的内存范围（即块）。</span><span class="sxs-lookup"><span data-stu-id="8ca23-118">Describes a range (that is, block) of memory that is undergoing garbage collection.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="8ca23-119">相关章节</span><span class="sxs-lookup"><span data-stu-id="8ca23-119">Related Sections</span></span>  
 <span data-ttu-id="8ca23-120">COR_DEBUG_IL_TO_NATIVE_MAP</span><span class="sxs-lookup"><span data-stu-id="8ca23-120">COR_DEBUG_IL_TO_NATIVE_MAP</span></span>  
  
 <span data-ttu-id="8ca23-121">COR_IL_MAP</span><span class="sxs-lookup"><span data-stu-id="8ca23-121">COR_IL_MAP</span></span>  
  
 [<span data-ttu-id="8ca23-122">分析概述</span><span class="sxs-lookup"><span data-stu-id="8ca23-122">Profiling Overview</span></span>](profiling-overview.md)  
  
 [<span data-ttu-id="8ca23-123">Profiling 接口</span><span class="sxs-lookup"><span data-stu-id="8ca23-123">Profiling Interfaces</span></span>](profiling-interfaces.md)  
  
 [<span data-ttu-id="8ca23-124">分析全局静态函数</span><span class="sxs-lookup"><span data-stu-id="8ca23-124">Profiling Global Static Functions</span></span>](profiling-global-static-functions.md)  
  
 [<span data-ttu-id="8ca23-125">分析枚举</span><span class="sxs-lookup"><span data-stu-id="8ca23-125">Profiling Enumerations</span></span>](profiling-enumerations.md)
