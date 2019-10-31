---
title: ICorDebugFrameEnum::Next 方法
ms.date: 03/30/2017
api_name:
- ICorDebugFrameEnum.Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFrameEnum::Next
helpviewer_keywords:
- ICorDebugFrameEnum::Next method [.NET Framework debugging]
- Next method, ICorDebugFrameEnum interface [.NET Framework debugging]
ms.assetid: 0bc96acb-6179-4328-a447-cda562ce9e98
topic_type:
- apiref
ms.openlocfilehash: ff74a9849b74b8a8e6b8c03f1fc4e7c7eee1ec14
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73124062"
---
# <a name="icordebugframeenumnext-method"></a><span data-ttu-id="efc64-102">ICorDebugFrameEnum::Next 方法</span><span class="sxs-lookup"><span data-stu-id="efc64-102">ICorDebugFrameEnum::Next Method</span></span>
<span data-ttu-id="efc64-103">从当前位置开始，获取指定数量的 ICorDebugFrame 实例。</span><span class="sxs-lookup"><span data-stu-id="efc64-103">Gets the specified number of ICorDebugFrame instances, starting at the current position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="efc64-104">语法</span><span class="sxs-lookup"><span data-stu-id="efc64-104">Syntax</span></span>  
  
```cpp  
HRESULT Next (  
    [in] ULONG  celt,  
    [out, size_is(celt), length_is(*pceltFetched)]  
        ICorDebugFrame *frames[],  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="efc64-105">参数</span><span class="sxs-lookup"><span data-stu-id="efc64-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="efc64-106">中要检索的 `ICorDebugFrame` 实例的数目。</span><span class="sxs-lookup"><span data-stu-id="efc64-106">[in] The number of `ICorDebugFrame` instances to be retrieved.</span></span>  
  
 `frames`  
 <span data-ttu-id="efc64-107">弄指针的数组，其中每个都指向一个 `ICorDebugFrame` 对象。</span><span class="sxs-lookup"><span data-stu-id="efc64-107">[out] An array of pointers, each of which points to an `ICorDebugFrame` object.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="efc64-108">弄一个指针，指向实际返回的 `ICorDebugFrame` 实例的数目。</span><span class="sxs-lookup"><span data-stu-id="efc64-108">[out] A pointer to the number of `ICorDebugFrame` instances actually returned.</span></span> <span data-ttu-id="efc64-109">如果 `celt` 为1，则此值可以为 null。</span><span class="sxs-lookup"><span data-stu-id="efc64-109">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="efc64-110">要求</span><span class="sxs-lookup"><span data-stu-id="efc64-110">Requirements</span></span>  
 <span data-ttu-id="efc64-111">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="efc64-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="efc64-112">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="efc64-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="efc64-113">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="efc64-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="efc64-114">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="efc64-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
