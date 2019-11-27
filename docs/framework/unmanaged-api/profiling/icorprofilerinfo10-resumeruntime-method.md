---
title: ICorProfilerInfo10::ResumeRuntime
ms.date: 08/06/2019
dev_langs:
- cpp
api_name:
- ICorProfilerInfo10.ResumeRuntime
api_location:
- mscorwks.dll
api_type:
- COM
author: davmason
ms.author: davmason
ms.openlocfilehash: 515b42d649f68345f9924f57a91d146556480e0a
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74449800"
---
# <a name="icorprofilerinfo10resumeruntime-method"></a><span data-ttu-id="c932f-102">ICorProfilerInfo10：： ResumeRuntime 方法</span><span class="sxs-lookup"><span data-stu-id="c932f-102">ICorProfilerInfo10::ResumeRuntime Method</span></span>

<span data-ttu-id="c932f-103">恢复运行时，而不执行 GC。</span><span class="sxs-lookup"><span data-stu-id="c932f-103">Resumes the runtime without performing a GC.</span></span>

## <a name="syntax"></a><span data-ttu-id="c932f-104">语法</span><span class="sxs-lookup"><span data-stu-id="c932f-104">Syntax</span></span>

```cpp
HRESULT ResumeRuntime();
```

## <a name="requirements"></a><span data-ttu-id="c932f-105">要求</span><span class="sxs-lookup"><span data-stu-id="c932f-105">Requirements</span></span>

<span data-ttu-id="c932f-106">**平台：** 请参阅[支持 .Net Core 的操作系统](../../../core/install/dependencies.md?tabs=netcore30&pivots=os-windows)。</span><span class="sxs-lookup"><span data-stu-id="c932f-106">**Platforms:** See [.NET Core supported operating systems](../../../core/install/dependencies.md?tabs=netcore30&pivots=os-windows).</span></span>

<span data-ttu-id="c932f-107">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="c932f-107">**Header:** CorProf.idl, CorProf.h</span></span>

<span data-ttu-id="c932f-108">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c932f-108">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="c932f-109">**.Net 版本：** [!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c932f-109">**.NET Versions:** [!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="c932f-110">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c932f-110">See also</span></span>

- [<span data-ttu-id="c932f-111">ICorProfilerInfo10 接口</span><span class="sxs-lookup"><span data-stu-id="c932f-111">ICorProfilerInfo10 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo10-interface.md)
