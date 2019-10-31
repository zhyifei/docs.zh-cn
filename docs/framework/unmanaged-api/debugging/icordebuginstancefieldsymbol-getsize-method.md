---
title: ICorDebugInstanceFieldSymbol：： GetSize 方法
ms.date: 03/30/2017
ms.assetid: a4af1e3b-6a9f-4855-95ba-5317565c8e2b
ms.openlocfilehash: 71828cd8486e2ff09190d23473dbab303b92f933
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73139019"
---
# <a name="icordebuginstancefieldsymbolgetsize-method"></a><span data-ttu-id="fc2e3-102">ICorDebugInstanceFieldSymbol：： GetSize 方法</span><span class="sxs-lookup"><span data-stu-id="fc2e3-102">ICorDebugInstanceFieldSymbol::GetSize Method</span></span>
<span data-ttu-id="fc2e3-103">获取实例字段的大小（以字节为单位）。</span><span class="sxs-lookup"><span data-stu-id="fc2e3-103">Gets the size in bytes of the instance field.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fc2e3-104">语法</span><span class="sxs-lookup"><span data-stu-id="fc2e3-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSize(  
   [out] ULONG32 *pcbSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fc2e3-105">参数</span><span class="sxs-lookup"><span data-stu-id="fc2e3-105">Parameters</span></span>  
 `pcbSize`  
 <span data-ttu-id="fc2e3-106">[out] 指向字段长度的指针。</span><span class="sxs-lookup"><span data-stu-id="fc2e3-106">[out] A pointer to length of the field.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fc2e3-107">备注</span><span class="sxs-lookup"><span data-stu-id="fc2e3-107">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="fc2e3-108">此方法仅适用于 .NET Native。</span><span class="sxs-lookup"><span data-stu-id="fc2e3-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fc2e3-109">要求</span><span class="sxs-lookup"><span data-stu-id="fc2e3-109">Requirements</span></span>  
 <span data-ttu-id="fc2e3-110">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="fc2e3-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fc2e3-111">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="fc2e3-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="fc2e3-112">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fc2e3-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fc2e3-113">**.NET Framework 版本：** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fc2e3-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fc2e3-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="fc2e3-114">See also</span></span>

- [<span data-ttu-id="fc2e3-115">ICorDebugInstanceFieldSymbol 接口</span><span class="sxs-lookup"><span data-stu-id="fc2e3-115">ICorDebugInstanceFieldSymbol Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuginstancefieldsymbol-interface.md)
- [<span data-ttu-id="fc2e3-116">调试接口</span><span class="sxs-lookup"><span data-stu-id="fc2e3-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
