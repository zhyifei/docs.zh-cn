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
ms.openlocfilehash: 49de3383902791b1278e7c9221a80c3454eb12a2
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/29/2020
ms.locfileid: "76868915"
---
# <a name="icorprofilerinfo10resumeruntime-method"></a><span data-ttu-id="0ba79-102">ICorProfilerInfo10：： ResumeRuntime 方法</span><span class="sxs-lookup"><span data-stu-id="0ba79-102">ICorProfilerInfo10::ResumeRuntime Method</span></span>

<span data-ttu-id="0ba79-103">恢复运行时，而不执行 GC。</span><span class="sxs-lookup"><span data-stu-id="0ba79-103">Resumes the runtime without performing a GC.</span></span>

## <a name="syntax"></a><span data-ttu-id="0ba79-104">语法</span><span class="sxs-lookup"><span data-stu-id="0ba79-104">Syntax</span></span>

```cpp
HRESULT ResumeRuntime();
```

## <a name="requirements"></a><span data-ttu-id="0ba79-105">需求</span><span class="sxs-lookup"><span data-stu-id="0ba79-105">Requirements</span></span>

<span data-ttu-id="0ba79-106">**平台：** 请参阅[支持 .Net Core 的操作系统](../../../core/install/dependencies.md?tabs=netcore30&pivots=os-windows)。</span><span class="sxs-lookup"><span data-stu-id="0ba79-106">**Platforms:** See [.NET Core supported operating systems](../../../core/install/dependencies.md?tabs=netcore30&pivots=os-windows).</span></span>

<span data-ttu-id="0ba79-107">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="0ba79-107">**Header:** CorProf.idl, CorProf.h</span></span>

<span data-ttu-id="0ba79-108">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0ba79-108">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="0ba79-109">**.Net 版本：** [!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0ba79-109">**.NET Versions:** [!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="0ba79-110">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0ba79-110">See also</span></span>

- [<span data-ttu-id="0ba79-111">ICorProfilerInfo10 接口</span><span class="sxs-lookup"><span data-stu-id="0ba79-111">ICorProfilerInfo10 Interface</span></span>](icorprofilerinfo10-interface.md)
