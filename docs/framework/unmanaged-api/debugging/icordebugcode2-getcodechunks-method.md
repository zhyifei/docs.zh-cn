---
title: ICorDebugCode2::GetCodeChunks 方法
ms.date: 03/30/2017
api_name:
- ICorDebugCode2.GetCodeChunks
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugCode2::GetCodeChunks
helpviewer_keywords:
- GetCodeChunks method [.NET Framework debugging]
- ICorDebugCode2::GetCodeChunks method [.NET Framework debugging]
ms.assetid: 210a2f02-2678-4555-bc4a-78a0408764c8
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1bdaf6391ca5c19f073708d6258ad5775bec9824
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/01/2019
ms.locfileid: "71700727"
---
# <a name="icordebugcode2getcodechunks-method"></a><span data-ttu-id="d4adb-102">ICorDebugCode2::GetCodeChunks 方法</span><span class="sxs-lookup"><span data-stu-id="d4adb-102">ICorDebugCode2::GetCodeChunks Method</span></span>

<span data-ttu-id="d4adb-103">获取包含此代码对象的代码块。</span><span class="sxs-lookup"><span data-stu-id="d4adb-103">Gets the chunks of code that this code object is composed of.</span></span>

## <a name="syntax"></a><span data-ttu-id="d4adb-104">语法</span><span class="sxs-lookup"><span data-stu-id="d4adb-104">Syntax</span></span>

```cpp
HRESULT GetCodeChunks (
    [in]  ULONG32     cbufSize,
    [out] ULONG32     *pcnumChunks,
    [out, size_is(cbufSize), length_is(*pcnumChunks)]
        CodeChunkInfo chunks[]
);
```

## <a name="parameters"></a><span data-ttu-id="d4adb-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="d4adb-105">Parameters</span></span>

 `cbufSize`  
 <span data-ttu-id="d4adb-106">中@No__t-0 数组的大小。</span><span class="sxs-lookup"><span data-stu-id="d4adb-106">[in] Size of the `chunks` array.</span></span>

 `pcnumChunks`  
 <span data-ttu-id="d4adb-107">弄@No__t-0 数组中返回的块区数。</span><span class="sxs-lookup"><span data-stu-id="d4adb-107">[out] The number of chunks returned in the `chunks` array.</span></span>

 `chunks`  
 <span data-ttu-id="d4adb-108">弄"CodeChunkInfo" 结构的数组，其中每个结构都表示一个代码块。</span><span class="sxs-lookup"><span data-stu-id="d4adb-108">[out] An array of "CodeChunkInfo" structures, each of which represents a single chunk of code.</span></span> <span data-ttu-id="d4adb-109">如果 @no__t 的值为0，则此参数可以为 null。</span><span class="sxs-lookup"><span data-stu-id="d4adb-109">If the value of `cbufSize` is 0, this parameter can be null.</span></span>

## <a name="remarks"></a><span data-ttu-id="d4adb-110">备注</span><span class="sxs-lookup"><span data-stu-id="d4adb-110">Remarks</span></span>

 <span data-ttu-id="d4adb-111">代码块将永远不会重叠，它们将遵循[ICorDebugCode：： GetCode](icordebugcode-getcode-method.md)连接的顺序。</span><span class="sxs-lookup"><span data-stu-id="d4adb-111">The code chunks will never overlap, and they will follow the order in which they would have been concatenated by [ICorDebugCode::GetCode](icordebugcode-getcode-method.md).</span></span> <span data-ttu-id="d4adb-112">.NET Framework 版本2.0 中的 Microsoft 中间语言（MSIL）代码对象将包含一个代码块。</span><span class="sxs-lookup"><span data-stu-id="d4adb-112">A Microsoft intermediate language (MSIL) code object in the .NET Framework version 2.0 will comprise a single code chunk.</span></span>

## <a name="requirements"></a><span data-ttu-id="d4adb-113">要求</span><span class="sxs-lookup"><span data-stu-id="d4adb-113">Requirements</span></span>

 <span data-ttu-id="d4adb-114">**适用**请参阅[系统需求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="d4adb-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

 <span data-ttu-id="d4adb-115">**标头：** Cordebug.idl，Cordebug.idl</span><span class="sxs-lookup"><span data-stu-id="d4adb-115">**Header:** CorDebug.idl, CorDebug.h</span></span>

 <span data-ttu-id="d4adb-116">**类库**CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d4adb-116">**Library:** CorGuids.lib</span></span>

 <span data-ttu-id="d4adb-117">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d4adb-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
 
