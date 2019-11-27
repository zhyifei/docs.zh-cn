---
title: ICorProfilerInfo10::SuspendRuntime
ms.date: 08/06/2019
dev_langs:
- cpp
api_name:
- ICorProfilerInfo10.SuspendRuntime
api_location:
- mscorwks.dll
api_type:
- COM
author: davmason
ms.author: davmason
ms.openlocfilehash: f5104c779f99ef9f26a9eccc00008ded62336d8e
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74426959"
---
# <a name="icorprofilerinfo10suspendruntime-method"></a><span data-ttu-id="5caf5-102">ICorProfilerInfo10：： SuspendRuntime 方法</span><span class="sxs-lookup"><span data-stu-id="5caf5-102">ICorProfilerInfo10::SuspendRuntime Method</span></span>

<span data-ttu-id="5caf5-103">挂起运行时，而不执行 GC。</span><span class="sxs-lookup"><span data-stu-id="5caf5-103">Suspends the runtime without performing a GC.</span></span>

## <a name="syntax"></a><span data-ttu-id="5caf5-104">语法</span><span class="sxs-lookup"><span data-stu-id="5caf5-104">Syntax</span></span>

```cpp
HRESULT SuspendRuntime();
```

## <a name="requirements"></a><span data-ttu-id="5caf5-105">要求</span><span class="sxs-lookup"><span data-stu-id="5caf5-105">Requirements</span></span>

<span data-ttu-id="5caf5-106">**平台：** 请参阅[支持 .Net Core 的操作系统](../../../core/install/dependencies.md?tabs=netcore30&pivots=os-windows)。</span><span class="sxs-lookup"><span data-stu-id="5caf5-106">**Platforms:** See [.NET Core supported operating systems](../../../core/install/dependencies.md?tabs=netcore30&pivots=os-windows).</span></span>

<span data-ttu-id="5caf5-107">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="5caf5-107">**Header:** CorProf.idl, CorProf.h</span></span>

<span data-ttu-id="5caf5-108">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5caf5-108">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="5caf5-109">**.Net 版本：** [!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5caf5-109">**.NET Versions:** [!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="5caf5-110">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5caf5-110">See also</span></span>

- [<span data-ttu-id="5caf5-111">ICorProfilerInfo10 接口</span><span class="sxs-lookup"><span data-stu-id="5caf5-111">ICorProfilerInfo10 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo10-interface.md)
