---
title: ICorDebugChainEnum::Next 方法
ms.date: 03/30/2017
api_name:
- ICorDebugChainEnum.Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugChainEnum::Next
helpviewer_keywords:
- ICorDebugChainEnum::Next method [.NET Framework debugging]
- Next method, ICorDebugChainEnum interface [.NET Framework debugging]
ms.assetid: 6b791351-bcc5-4ddd-9cab-eff2f7dd5142
topic_type:
- apiref
ms.openlocfilehash: 3c11a0547ad5acc5613324d7e9d7439d44549dbc
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73125816"
---
# <a name="icordebugchainenumnext-method"></a><span data-ttu-id="ab4a3-102">ICorDebugChainEnum::Next 方法</span><span class="sxs-lookup"><span data-stu-id="ab4a3-102">ICorDebugChainEnum::Next Method</span></span>
<span data-ttu-id="ab4a3-103">从当前位置开始，从枚举中获取指定数量的 ICorDebugChain 实例。</span><span class="sxs-lookup"><span data-stu-id="ab4a3-103">Gets the specified number of ICorDebugChain instances from the enumeration, starting at the current position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ab4a3-104">语法</span><span class="sxs-lookup"><span data-stu-id="ab4a3-104">Syntax</span></span>  
  
```cpp  
HRESULT Next (  
    [in] ULONG  celt,  
    [out, size_is(celt), length_is(*pceltFetched)]  
        ICorDebugChain *chains[],  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ab4a3-105">参数</span><span class="sxs-lookup"><span data-stu-id="ab4a3-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="ab4a3-106">中要检索的 `ICorDebugChain` 实例的数目。</span><span class="sxs-lookup"><span data-stu-id="ab4a3-106">[in] The number of `ICorDebugChain` instances to be retrieved.</span></span>  
  
 `chains`  
 <span data-ttu-id="ab4a3-107">弄一个指针数组，其中每个指针指向一个表示链的 `ICorDebugChain` 对象。</span><span class="sxs-lookup"><span data-stu-id="ab4a3-107">[out] An array of pointers, each of which points to an `ICorDebugChain` object that represents a chain.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="ab4a3-108">弄一个指针，指向实际返回的 `ICorDebugChain` 实例的数目。</span><span class="sxs-lookup"><span data-stu-id="ab4a3-108">[out] A pointer to the number of `ICorDebugChain` instances actually returned.</span></span> <span data-ttu-id="ab4a3-109">如果 `celt` 为1，则此值可以为 null。</span><span class="sxs-lookup"><span data-stu-id="ab4a3-109">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ab4a3-110">要求</span><span class="sxs-lookup"><span data-stu-id="ab4a3-110">Requirements</span></span>  
 <span data-ttu-id="ab4a3-111">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="ab4a3-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ab4a3-112">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ab4a3-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ab4a3-113">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ab4a3-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ab4a3-114">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ab4a3-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
