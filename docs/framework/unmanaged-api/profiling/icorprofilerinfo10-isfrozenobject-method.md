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
ms.openlocfilehash: d212c06c7ddc9f22095c0b95f19fd1083482435c
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/21/2019
ms.locfileid: "69661225"
---
# <a name="icorprofilerinfo10isfrozenobject-method"></a><span data-ttu-id="b012e-102">ICorProfilerInfo10:: IsFrozenObject 方法</span><span class="sxs-lookup"><span data-stu-id="b012e-102">ICorProfilerInfo10::IsFrozenObject Method</span></span>

<span data-ttu-id="b012e-103">给定 ObjectID, 确定对象是否位于只读段。</span><span class="sxs-lookup"><span data-stu-id="b012e-103">Given an ObjectID, determines whether the object is in a read-only segment.</span></span>

## <a name="syntax"></a><span data-ttu-id="b012e-104">语法</span><span class="sxs-lookup"><span data-stu-id="b012e-104">Syntax</span></span>

```cpp
HRESULT IsFrozenObject( [in]  ObjectID objectId,
                        [out] BOOL *pbFrozen);
```

#### <a name="parameters"></a><span data-ttu-id="b012e-105">参数</span><span class="sxs-lookup"><span data-stu-id="b012e-105">Parameters</span></span>

`objectId` \
<span data-ttu-id="b012e-106">中要检查的对象。</span><span class="sxs-lookup"><span data-stu-id="b012e-106">[in] The object to examine.</span></span>

`pbFrozen` \
<span data-ttu-id="b012e-107">弄一个`BOOL` , 该值指示对象是否位于只读段中。</span><span class="sxs-lookup"><span data-stu-id="b012e-107">[out] A `BOOL` indicating if the object is in a read-only segment.</span></span>

## <a name="requirements"></a><span data-ttu-id="b012e-108">要求</span><span class="sxs-lookup"><span data-stu-id="b012e-108">Requirements</span></span>

<span data-ttu-id="b012e-109">**适用**请参阅[支持 .Net Core 的操作系统](../../../core/windows-prerequisites.md#net-core-supported-operating-systems)。</span><span class="sxs-lookup"><span data-stu-id="b012e-109">**Platforms:** See [.NET Core supported operating systems](../../../core/windows-prerequisites.md#net-core-supported-operating-systems).</span></span>

<span data-ttu-id="b012e-110">**标头：** Corprof.idl, Corprof.idl</span><span class="sxs-lookup"><span data-stu-id="b012e-110">**Header:** CorProf.idl, CorProf.h</span></span>

<span data-ttu-id="b012e-111">**类库**CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b012e-111">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="b012e-112">**.Net 版本:** [!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b012e-112">**.NET Versions:** [!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="b012e-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="b012e-113">See also</span></span>

- [<span data-ttu-id="b012e-114">ICorProfilerInfo10 接口</span><span class="sxs-lookup"><span data-stu-id="b012e-114">ICorProfilerInfo10 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo10-interface.md)
