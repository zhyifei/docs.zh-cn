---
title: ICorProfilerInfo8 接口
ms.date: 08/06/2019
author: davmason
ms.author: davmason
ms.openlocfilehash: 2baa33a7a3527392d8095b5d0ec7ad6af8a71a8e
ms.sourcegitcommit: 33c8d6f7342a4bb2c577842b7f075b0e20a2fa40
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/12/2019
ms.locfileid: "70928939"
---
# <a name="icorprofilerinfo8-interface"></a><span data-ttu-id="6b54e-102">ICorProfilerInfo8 接口</span><span class="sxs-lookup"><span data-stu-id="6b54e-102">ICorProfilerInfo8 Interface</span></span>

<span data-ttu-id="6b54e-103">[ICorProfilerInfo7](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo7-interface.md)的子类，提供查询有关动态方法的信息的方法。</span><span class="sxs-lookup"><span data-stu-id="6b54e-103">A subclass of [ICorProfilerInfo7](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo7-interface.md) that provides methods to query information about dynamic methods.</span></span>

## <a name="methods"></a><span data-ttu-id="6b54e-104">方法</span><span class="sxs-lookup"><span data-stu-id="6b54e-104">Methods</span></span>  

| <span data-ttu-id="6b54e-105">方法</span><span class="sxs-lookup"><span data-stu-id="6b54e-105">Method</span></span>|<span data-ttu-id="6b54e-106">描述</span><span class="sxs-lookup"><span data-stu-id="6b54e-106">Description</span></span>|  
| ------------|-----------------|  
|[<span data-ttu-id="6b54e-107">IsFunctionDynamic 方法</span><span class="sxs-lookup"><span data-stu-id="6b54e-107">IsFunctionDynamic Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo8-isfunctiondynamic-method.md)| <span data-ttu-id="6b54e-108">确定函数是否没有关联的元数据。</span><span class="sxs-lookup"><span data-stu-id="6b54e-108">Determines if a function does not have associated metadata.</span></span>|
|[<span data-ttu-id="6b54e-109">GetFunctionFromIP3 方法</span><span class="sxs-lookup"><span data-stu-id="6b54e-109">GetFunctionFromIP3 Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo8-getfunctionfromip3-method.md)| <span data-ttu-id="6b54e-110">将托管代码指令指针映射到 FunctionID。</span><span class="sxs-lookup"><span data-stu-id="6b54e-110">Maps a managed code instruction pointer to a FunctionID.</span></span> <span data-ttu-id="6b54e-111">此方法适用于动态和非动态方法。</span><span class="sxs-lookup"><span data-stu-id="6b54e-111">This method works for both dynamic and non-dynamic methods.</span></span> |
|[<span data-ttu-id="6b54e-112">GetDynamicFunctionInfo 方法</span><span class="sxs-lookup"><span data-stu-id="6b54e-112">GetDynamicFunctionInfo Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo8-getdynamicfunctioninfo-method.md)| <span data-ttu-id="6b54e-113">检索有关动态方法的信息。</span><span class="sxs-lookup"><span data-stu-id="6b54e-113">Retrieves information about dynamic methods.</span></span> |

## <a name="requirements"></a><span data-ttu-id="6b54e-114">要求</span><span class="sxs-lookup"><span data-stu-id="6b54e-114">Requirements</span></span>  
<span data-ttu-id="6b54e-115">**适用**请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="6b54e-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="6b54e-116">**标头：** Corprof.idl，Corprof.idl</span><span class="sxs-lookup"><span data-stu-id="6b54e-116">**Header:** CorProf.idl, CorProf.h</span></span>  
<span data-ttu-id="6b54e-117">**.NET Framework 版本：** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="6b54e-117">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="6b54e-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="6b54e-118">See also</span></span>

- [<span data-ttu-id="6b54e-119">Profiling 接口</span><span class="sxs-lookup"><span data-stu-id="6b54e-119">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
