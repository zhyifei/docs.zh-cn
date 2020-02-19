---
title: ICorProfilerInfo10::IsFrozenObject
ms.date: 08/06/2019
dev_langs:
- cpp
api_name:
- ICorProfilerInfo10.IsFrozenObject
api_location:
- mscorwks.dll
api_type:
- COM
author: davmason
ms.author: davmason
ms.openlocfilehash: 21f9cb415f913a9c865a487f6e80523344db811e
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "77452183"
---
# <a name="icorprofilerinfo10isfrozenobject-method"></a><span data-ttu-id="bd6dd-102">ICorProfilerInfo10：： IsFrozenObject 方法</span><span class="sxs-lookup"><span data-stu-id="bd6dd-102">ICorProfilerInfo10::IsFrozenObject Method</span></span>

<span data-ttu-id="bd6dd-103">给定 ObjectID，确定对象是否位于只读段。</span><span class="sxs-lookup"><span data-stu-id="bd6dd-103">Given an ObjectID, determines whether the object is in a read-only segment.</span></span>

## <a name="syntax"></a><span data-ttu-id="bd6dd-104">语法</span><span class="sxs-lookup"><span data-stu-id="bd6dd-104">Syntax</span></span>

```cpp
HRESULT IsFrozenObject( [in]  ObjectID objectId,
                        [out] BOOL *pbFrozen);
```

## <a name="parameters"></a><span data-ttu-id="bd6dd-105">参数</span><span class="sxs-lookup"><span data-stu-id="bd6dd-105">Parameters</span></span>

- `objectId`

  <span data-ttu-id="bd6dd-106">\[中] 要检查的对象。</span><span class="sxs-lookup"><span data-stu-id="bd6dd-106">\[in] The object to examine.</span></span>

- `pbFrozen`

  <span data-ttu-id="bd6dd-107">\[out] 一个 `BOOL`，该值指示对象是否位于只读段中。</span><span class="sxs-lookup"><span data-stu-id="bd6dd-107">\[out] A `BOOL` indicating if the object is in a read-only segment.</span></span>

## <a name="requirements"></a><span data-ttu-id="bd6dd-108">要求</span><span class="sxs-lookup"><span data-stu-id="bd6dd-108">Requirements</span></span>

<span data-ttu-id="bd6dd-109">**平台：** 请参阅[支持 .Net Core 的操作系统](../../../core/install/dependencies.md?pivots=os-windows)。</span><span class="sxs-lookup"><span data-stu-id="bd6dd-109">**Platforms:** See [.NET Core supported operating systems](../../../core/install/dependencies.md?pivots=os-windows).</span></span>

<span data-ttu-id="bd6dd-110">**头文件：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="bd6dd-110">**Header:** CorProf.idl, CorProf.h</span></span>

<span data-ttu-id="bd6dd-111">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bd6dd-111">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="bd6dd-112">**.Net 版本：** [!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bd6dd-112">**.NET Versions:** [!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="bd6dd-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="bd6dd-113">See also</span></span>

- [<span data-ttu-id="bd6dd-114">ICorProfilerInfo10 接口</span><span class="sxs-lookup"><span data-stu-id="bd6dd-114">ICorProfilerInfo10 Interface</span></span>](icorprofilerinfo10-interface.md)
