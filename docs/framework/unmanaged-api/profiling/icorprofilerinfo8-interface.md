---
title: ICorProfilerInfo8 接口
ms.date: 08/06/2019
author: davmason
ms.author: davmason
ms.openlocfilehash: 476bcbd91188e3ff9eb63f50cfa2118a440b1a69
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/29/2020
ms.locfileid: "76868312"
---
# <a name="icorprofilerinfo8-interface"></a><span data-ttu-id="41a52-102">ICorProfilerInfo8 接口</span><span class="sxs-lookup"><span data-stu-id="41a52-102">ICorProfilerInfo8 Interface</span></span>

<span data-ttu-id="41a52-103">[ICorProfilerInfo7](icorprofilerinfo7-interface.md)的子类，提供查询有关动态方法的信息的方法。</span><span class="sxs-lookup"><span data-stu-id="41a52-103">A subclass of [ICorProfilerInfo7](icorprofilerinfo7-interface.md) that provides methods to query information about dynamic methods.</span></span>

## <a name="methods"></a><span data-ttu-id="41a52-104">方法</span><span class="sxs-lookup"><span data-stu-id="41a52-104">Methods</span></span>  

| <span data-ttu-id="41a52-105">方法</span><span class="sxs-lookup"><span data-stu-id="41a52-105">Method</span></span>|<span data-ttu-id="41a52-106">描述</span><span class="sxs-lookup"><span data-stu-id="41a52-106">Description</span></span>|  
| ------------|-----------------|  
|[<span data-ttu-id="41a52-107">IsFunctionDynamic 方法</span><span class="sxs-lookup"><span data-stu-id="41a52-107">IsFunctionDynamic Method</span></span>](icorprofilerinfo8-isfunctiondynamic-method.md)| <span data-ttu-id="41a52-108">确定函数是否没有关联的元数据。</span><span class="sxs-lookup"><span data-stu-id="41a52-108">Determines if a function does not have associated metadata.</span></span>|
|[<span data-ttu-id="41a52-109">GetFunctionFromIP3 方法</span><span class="sxs-lookup"><span data-stu-id="41a52-109">GetFunctionFromIP3 Method</span></span>](icorprofilerinfo8-getfunctionfromip3-method.md)| <span data-ttu-id="41a52-110">将托管代码指令指针映射到 FunctionID。</span><span class="sxs-lookup"><span data-stu-id="41a52-110">Maps a managed code instruction pointer to a FunctionID.</span></span> <span data-ttu-id="41a52-111">此方法适用于动态和非动态方法。</span><span class="sxs-lookup"><span data-stu-id="41a52-111">This method works for both dynamic and non-dynamic methods.</span></span> |
|[<span data-ttu-id="41a52-112">GetDynamicFunctionInfo 方法</span><span class="sxs-lookup"><span data-stu-id="41a52-112">GetDynamicFunctionInfo Method</span></span>](icorprofilerinfo8-getdynamicfunctioninfo-method.md)| <span data-ttu-id="41a52-113">检索有关动态方法的信息。</span><span class="sxs-lookup"><span data-stu-id="41a52-113">Retrieves information about dynamic methods.</span></span> |

## <a name="requirements"></a><span data-ttu-id="41a52-114">需求</span><span class="sxs-lookup"><span data-stu-id="41a52-114">Requirements</span></span>  
<span data-ttu-id="41a52-115">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="41a52-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="41a52-116">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="41a52-116">**Header:** CorProf.idl, CorProf.h</span></span>  
<span data-ttu-id="41a52-117">**.NET Framework 版本：** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="41a52-117">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="41a52-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="41a52-118">See also</span></span>

- [<span data-ttu-id="41a52-119">Profiling 接口</span><span class="sxs-lookup"><span data-stu-id="41a52-119">Profiling Interfaces</span></span>](profiling-interfaces.md)
