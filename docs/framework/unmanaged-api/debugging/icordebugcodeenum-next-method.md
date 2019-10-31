---
title: ICorDebugCodeEnum::Next 方法
ms.date: 03/30/2017
api_name:
- ICorDebugCodeEnum.Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugCodeEnum::Next
helpviewer_keywords:
- ICorDebugCodeEnum::Next method [.NET Framework debugging]
- Next method, ICorDebugEnum interface [.NET Framework debugging]
ms.assetid: 644ece86-384d-4c63-9fba-52c789616ff7
topic_type:
- apiref
ms.openlocfilehash: 04c36d1e5f0e79b71963683a3b613a9ad7392bcf
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73125529"
---
# <a name="icordebugcodeenumnext-method"></a><span data-ttu-id="e3783-102">ICorDebugCodeEnum::Next 方法</span><span class="sxs-lookup"><span data-stu-id="e3783-102">ICorDebugCodeEnum::Next Method</span></span>

<span data-ttu-id="e3783-103">从当前位置开始，从枚举中获取指定的 "ICorDebugCode" 实例数。</span><span class="sxs-lookup"><span data-stu-id="e3783-103">Gets the specified number of "ICorDebugCode" instances from the enumeration, starting at the current position.</span></span>

## <a name="syntax"></a><span data-ttu-id="e3783-104">语法</span><span class="sxs-lookup"><span data-stu-id="e3783-104">Syntax</span></span>

```cpp
HRESULT Next (
    [in] ULONG  celt,
    [out, size_is(celt), length_is(*pceltFetched)]
        ICorDebugCode *values[],
    [out] ULONG *pceltFetched
);
```

## <a name="parameters"></a><span data-ttu-id="e3783-105">参数</span><span class="sxs-lookup"><span data-stu-id="e3783-105">Parameters</span></span>

`celt`  
<span data-ttu-id="e3783-106">中要检索的 `ICorDebugCode` 实例的数目。</span><span class="sxs-lookup"><span data-stu-id="e3783-106">[in] The number of `ICorDebugCode` instances to be retrieved.</span></span>

`values`  
<span data-ttu-id="e3783-107">弄指针的数组，其中每个都指向一个 `ICorDebugCode` 对象。</span><span class="sxs-lookup"><span data-stu-id="e3783-107">[out] An array of pointers, each of which points to an `ICorDebugCode` object.</span></span>

`pceltFetched`  
<span data-ttu-id="e3783-108">弄一个指针，指向实际返回的 `ICorDebugCode` 实例的数目。</span><span class="sxs-lookup"><span data-stu-id="e3783-108">[out] A pointer to the number of `ICorDebugCode` instances actually returned.</span></span> <span data-ttu-id="e3783-109">如果 `celt` 为1，则此值可以为 null。</span><span class="sxs-lookup"><span data-stu-id="e3783-109">This value may be null if `celt` is one.</span></span>

## <a name="requirements"></a><span data-ttu-id="e3783-110">要求</span><span class="sxs-lookup"><span data-stu-id="e3783-110">Requirements</span></span>

<span data-ttu-id="e3783-111">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="e3783-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

<span data-ttu-id="e3783-112">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e3783-112">**Header:** CorDebug.idl, CorDebug.h</span></span>

<span data-ttu-id="e3783-113">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e3783-113">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="e3783-114">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e3783-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
