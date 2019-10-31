---
title: ICorDebugVariableSymbol：： GetSlotIndex 方法
ms.date: 03/30/2017
ms.assetid: 09c19f5f-afc4-4e0c-bffe-cd7147bc7a43
ms.openlocfilehash: a7a7ecf7d3e3d0d2125b03d3604c44138a2be0cc
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73120976"
---
# <a name="icordebugvariablesymbolgetslotindex-method"></a><span data-ttu-id="5f8e4-102">ICorDebugVariableSymbol：： GetSlotIndex 方法</span><span class="sxs-lookup"><span data-stu-id="5f8e4-102">ICorDebugVariableSymbol::GetSlotIndex Method</span></span>
<span data-ttu-id="5f8e4-103">获取本地变量的托管槽索引。</span><span class="sxs-lookup"><span data-stu-id="5f8e4-103">Gets the managed slot index of a local variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5f8e4-104">语法</span><span class="sxs-lookup"><span data-stu-id="5f8e4-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSlotIndex(  
   [out] ULONG32 *pSlotIndex  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5f8e4-105">参数</span><span class="sxs-lookup"><span data-stu-id="5f8e4-105">Parameters</span></span>  
 `pSlotIndex`  
 <span data-ttu-id="5f8e4-106">[out] 指向本地变量的槽索引的指针。</span><span class="sxs-lookup"><span data-stu-id="5f8e4-106">[out] A pointer to the local variable's slot index.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5f8e4-107">返回值</span><span class="sxs-lookup"><span data-stu-id="5f8e4-107">Return Value</span></span>  
 <span data-ttu-id="5f8e4-108">`S_OK` 如果成功。</span><span class="sxs-lookup"><span data-stu-id="5f8e4-108">`S_OK` if successful.</span></span> <span data-ttu-id="5f8e4-109">如果变量是一个函数自变量，则为 `E_FAIL`。</span><span class="sxs-lookup"><span data-stu-id="5f8e4-109">`E_FAIL` if the variable is a function argument.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5f8e4-110">备注</span><span class="sxs-lookup"><span data-stu-id="5f8e4-110">Remarks</span></span>  
 <span data-ttu-id="5f8e4-111">本地变量的托管槽索引可用于检索变量的元数据信息</span><span class="sxs-lookup"><span data-stu-id="5f8e4-111">The managed slot index of a local variable can be used to retrieve the variable's metadata information</span></span>  
  
> [!NOTE]
> <span data-ttu-id="5f8e4-112">此方法仅适用于 .NET Native。</span><span class="sxs-lookup"><span data-stu-id="5f8e4-112">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5f8e4-113">要求</span><span class="sxs-lookup"><span data-stu-id="5f8e4-113">Requirements</span></span>  
 <span data-ttu-id="5f8e4-114">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="5f8e4-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5f8e4-115">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5f8e4-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5f8e4-116">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5f8e4-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5f8e4-117">**.NET Framework 版本：** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5f8e4-117">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5f8e4-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="5f8e4-118">See also</span></span>

- [<span data-ttu-id="5f8e4-119">ICorDebugVariableSymbol 接口</span><span class="sxs-lookup"><span data-stu-id="5f8e4-119">ICorDebugVariableSymbol Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablesymbol-interface.md)
- [<span data-ttu-id="5f8e4-120">调试接口</span><span class="sxs-lookup"><span data-stu-id="5f8e4-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
