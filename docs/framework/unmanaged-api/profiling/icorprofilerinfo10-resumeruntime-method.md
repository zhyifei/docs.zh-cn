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
ms.openlocfilehash: cf599e5ded73b09d54c98dcd99f51b30c6a4ba82
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/21/2019
ms.locfileid: "69661211"
---
# <a name="icorprofilerinfo10resumeruntime-method"></a><span data-ttu-id="f09a2-102">ICorProfilerInfo10:: ResumeRuntime 方法</span><span class="sxs-lookup"><span data-stu-id="f09a2-102">ICorProfilerInfo10::ResumeRuntime Method</span></span>

<span data-ttu-id="f09a2-103">恢复运行时, 而不执行 GC。</span><span class="sxs-lookup"><span data-stu-id="f09a2-103">Resumes the runtime without performing a GC.</span></span>

## <a name="syntax"></a><span data-ttu-id="f09a2-104">语法</span><span class="sxs-lookup"><span data-stu-id="f09a2-104">Syntax</span></span>

```cpp
HRESULT ResumeRuntime();
```

## <a name="requirements"></a><span data-ttu-id="f09a2-105">要求</span><span class="sxs-lookup"><span data-stu-id="f09a2-105">Requirements</span></span>

<span data-ttu-id="f09a2-106">**适用**请参阅[支持 .Net Core 的操作系统](../../../core/windows-prerequisites.md#net-core-supported-operating-systems)。</span><span class="sxs-lookup"><span data-stu-id="f09a2-106">**Platforms:** See [.NET Core supported operating systems](../../../core/windows-prerequisites.md#net-core-supported-operating-systems).</span></span>

<span data-ttu-id="f09a2-107">**标头：** Corprof.idl, Corprof.idl</span><span class="sxs-lookup"><span data-stu-id="f09a2-107">**Header:** CorProf.idl, CorProf.h</span></span>

<span data-ttu-id="f09a2-108">**类库**CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f09a2-108">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="f09a2-109">**.Net 版本:** [!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f09a2-109">**.NET Versions:** [!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="f09a2-110">请参阅</span><span class="sxs-lookup"><span data-stu-id="f09a2-110">See also</span></span>

- [<span data-ttu-id="f09a2-111">ICorProfilerInfo10 接口</span><span class="sxs-lookup"><span data-stu-id="f09a2-111">ICorProfilerInfo10 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo10-interface.md)
