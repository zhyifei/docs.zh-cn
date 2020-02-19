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
ms.openlocfilehash: 8d00718579f44a164cd83e2b05d41f70f1c65785
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "77452144"
---
# <a name="icorprofilerinfo10suspendruntime-method"></a><span data-ttu-id="3f72d-102">ICorProfilerInfo10：： SuspendRuntime 方法</span><span class="sxs-lookup"><span data-stu-id="3f72d-102">ICorProfilerInfo10::SuspendRuntime Method</span></span>

<span data-ttu-id="3f72d-103">挂起运行时，而不执行 GC。</span><span class="sxs-lookup"><span data-stu-id="3f72d-103">Suspends the runtime without performing a GC.</span></span>

## <a name="syntax"></a><span data-ttu-id="3f72d-104">语法</span><span class="sxs-lookup"><span data-stu-id="3f72d-104">Syntax</span></span>

```cpp
HRESULT SuspendRuntime();
```

## <a name="requirements"></a><span data-ttu-id="3f72d-105">要求</span><span class="sxs-lookup"><span data-stu-id="3f72d-105">Requirements</span></span>

<span data-ttu-id="3f72d-106">**平台：** 请参阅[支持 .Net Core 的操作系统](../../../core/install/dependencies.md?pivots=os-windows)。</span><span class="sxs-lookup"><span data-stu-id="3f72d-106">**Platforms:** See [.NET Core supported operating systems](../../../core/install/dependencies.md?pivots=os-windows).</span></span>

<span data-ttu-id="3f72d-107">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="3f72d-107">**Header:** CorProf.idl, CorProf.h</span></span>

<span data-ttu-id="3f72d-108">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3f72d-108">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="3f72d-109">**.Net 版本：** [!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3f72d-109">**.NET Versions:** [!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="3f72d-110">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3f72d-110">See also</span></span>

- [<span data-ttu-id="3f72d-111">ICorProfilerInfo10 接口</span><span class="sxs-lookup"><span data-stu-id="3f72d-111">ICorProfilerInfo10 Interface</span></span>](icorprofilerinfo10-interface.md)
