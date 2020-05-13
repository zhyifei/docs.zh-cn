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
ms.openlocfilehash: 4652e4b34d614ad3b7b852925fcc63309bdd1498
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/12/2020
ms.locfileid: "83209456"
---
# <a name="icordebugframeenumnext-method"></a><span data-ttu-id="bf552-102">ICorDebugFrameEnum::Next 方法</span><span class="sxs-lookup"><span data-stu-id="bf552-102">ICorDebugFrameEnum::Next Method</span></span>
<span data-ttu-id="bf552-103">从当前位置开始，获取指定数量的 ICorDebugFrame 实例。</span><span class="sxs-lookup"><span data-stu-id="bf552-103">Gets the specified number of ICorDebugFrame instances, starting at the current position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bf552-104">语法</span><span class="sxs-lookup"><span data-stu-id="bf552-104">Syntax</span></span>  
  
```cpp  
HRESULT Next (  
    [in] ULONG  celt,  
    [out, size_is(celt), length_is(*pceltFetched)]  
        ICorDebugFrame *frames[],  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bf552-105">参数</span><span class="sxs-lookup"><span data-stu-id="bf552-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="bf552-106">中`ICorDebugFrame`要检索的实例数。</span><span class="sxs-lookup"><span data-stu-id="bf552-106">[in] The number of `ICorDebugFrame` instances to be retrieved.</span></span>  
  
 `frames`  
 <span data-ttu-id="bf552-107">弄指针的数组，其中每个都指向一个 `ICorDebugFrame` 对象。</span><span class="sxs-lookup"><span data-stu-id="bf552-107">[out] An array of pointers, each of which points to an `ICorDebugFrame` object.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="bf552-108">弄一个指针，指向 `ICorDebugFrame` 实际返回的实例数。</span><span class="sxs-lookup"><span data-stu-id="bf552-108">[out] A pointer to the number of `ICorDebugFrame` instances actually returned.</span></span> <span data-ttu-id="bf552-109">如果为1，则此值可以为 null `celt` 。</span><span class="sxs-lookup"><span data-stu-id="bf552-109">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bf552-110">要求</span><span class="sxs-lookup"><span data-stu-id="bf552-110">Requirements</span></span>  
 <span data-ttu-id="bf552-111">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="bf552-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bf552-112">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="bf552-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="bf552-113">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bf552-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="bf552-114">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bf552-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
