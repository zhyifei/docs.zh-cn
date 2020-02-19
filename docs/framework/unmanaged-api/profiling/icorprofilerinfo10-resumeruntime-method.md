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
ms.openlocfilehash: a3dca2cbb138dbc43f477488032e67335c8b15f9
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "77452157"
---
# <a name="icorprofilerinfo10resumeruntime-method"></a><span data-ttu-id="18fb7-102">ICorProfilerInfo10：： ResumeRuntime 方法</span><span class="sxs-lookup"><span data-stu-id="18fb7-102">ICorProfilerInfo10::ResumeRuntime Method</span></span>

<span data-ttu-id="18fb7-103">恢复运行时，而不执行 GC。</span><span class="sxs-lookup"><span data-stu-id="18fb7-103">Resumes the runtime without performing a GC.</span></span>

## <a name="syntax"></a><span data-ttu-id="18fb7-104">语法</span><span class="sxs-lookup"><span data-stu-id="18fb7-104">Syntax</span></span>

```cpp
HRESULT ResumeRuntime();
```

## <a name="requirements"></a><span data-ttu-id="18fb7-105">要求</span><span class="sxs-lookup"><span data-stu-id="18fb7-105">Requirements</span></span>

<span data-ttu-id="18fb7-106">**平台：** 请参阅[支持 .Net Core 的操作系统](../../../core/install/dependencies.md?pivots=os-windows)。</span><span class="sxs-lookup"><span data-stu-id="18fb7-106">**Platforms:** See [.NET Core supported operating systems](../../../core/install/dependencies.md?pivots=os-windows).</span></span>

<span data-ttu-id="18fb7-107">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="18fb7-107">**Header:** CorProf.idl, CorProf.h</span></span>

<span data-ttu-id="18fb7-108">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="18fb7-108">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="18fb7-109">**.Net 版本：** [!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]</span><span class="sxs-lookup"><span data-stu-id="18fb7-109">**.NET Versions:** [!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="18fb7-110">另请参阅</span><span class="sxs-lookup"><span data-stu-id="18fb7-110">See also</span></span>

- [<span data-ttu-id="18fb7-111">ICorProfilerInfo10 接口</span><span class="sxs-lookup"><span data-stu-id="18fb7-111">ICorProfilerInfo10 Interface</span></span>](icorprofilerinfo10-interface.md)
