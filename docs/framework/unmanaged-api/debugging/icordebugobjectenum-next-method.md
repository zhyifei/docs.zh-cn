---
title: ICorDebugObjectEnum::Next 方法
ms.date: 03/30/2017
api_name:
- ICorDebugObjectEnum.Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugObjectEnum::Next
helpviewer_keywords:
- Next method, ICorDebugObjectEnum interface [.NET Framework debugging]
- ICorDebugObjectEnum::Next method [.NET Framework debugging]
ms.assetid: 10093e3d-26b6-4ad7-8ef3-bbf66243fc02
topic_type:
- apiref
ms.openlocfilehash: adcfbf1207ad7895ab55f7e5cf9581905cb826bf
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73096105"
---
# <a name="icordebugobjectenumnext-method"></a><span data-ttu-id="ac279-102">ICorDebugObjectEnum::Next 方法</span><span class="sxs-lookup"><span data-stu-id="ac279-102">ICorDebugObjectEnum::Next Method</span></span>
<span data-ttu-id="ac279-103">从当前位置开始，获取枚举中指定数量的对象的相对虚拟地址（Rva）。</span><span class="sxs-lookup"><span data-stu-id="ac279-103">Gets the relative virtual addresses (RVAs) of the specified number of objects from the enumeration, starting at the current position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ac279-104">语法</span><span class="sxs-lookup"><span data-stu-id="ac279-104">Syntax</span></span>  
  
```cpp  
HRESULT Next (  
    [in] ULONG celt,  
    [out, size_is(celt), length_is(*pceltFetched)]    
        CORDB_ADDRESS objects[],  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ac279-105">参数</span><span class="sxs-lookup"><span data-stu-id="ac279-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="ac279-106">[in] 要检索的对象数。</span><span class="sxs-lookup"><span data-stu-id="ac279-106">[in] The number of objects to be retrieved.</span></span>  
  
 `objects`  
 <span data-ttu-id="ac279-107">弄指针的数组，其中每个指针指向一个 CORDB_ADDRESS 对象。</span><span class="sxs-lookup"><span data-stu-id="ac279-107">[out] An array of pointers, each of which points to a CORDB_ADDRESS object.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="ac279-108">弄一个指针，指向实际返回的对象数。</span><span class="sxs-lookup"><span data-stu-id="ac279-108">[out] Pointer to the number of objects actually returned.</span></span> <span data-ttu-id="ac279-109">如果 `celt` 为1，则此值可以为 null。</span><span class="sxs-lookup"><span data-stu-id="ac279-109">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ac279-110">要求</span><span class="sxs-lookup"><span data-stu-id="ac279-110">Requirements</span></span>  
 <span data-ttu-id="ac279-111">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="ac279-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ac279-112">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ac279-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ac279-113">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ac279-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ac279-114">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ac279-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ac279-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="ac279-115">See also</span></span>
