---
title: "ICorDebugVariableSymbol::GetSlotIndex 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 09c19f5f-afc4-4e0c-bffe-cd7147bc7a43
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: abb84e529768e0be44883511bb89703a4c3199df
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugvariablesymbolgetslotindex-method"></a><span data-ttu-id="f1599-102">ICorDebugVariableSymbol::GetSlotIndex 方法</span><span class="sxs-lookup"><span data-stu-id="f1599-102">ICorDebugVariableSymbol::GetSlotIndex Method</span></span>
<span data-ttu-id="f1599-103">获取本地变量的托管槽索引。</span><span class="sxs-lookup"><span data-stu-id="f1599-103">Gets the managed slot index of a local variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f1599-104">语法</span><span class="sxs-lookup"><span data-stu-id="f1599-104">Syntax</span></span>  
  
```  
HRESULT GetSlotIndex(  
   [out] ULONG32 *pSlotIndex  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="f1599-105">参数</span><span class="sxs-lookup"><span data-stu-id="f1599-105">Parameters</span></span>  
 `pSlotIndex`  
 <span data-ttu-id="f1599-106">[out] 指向本地变量的槽索引的指针。</span><span class="sxs-lookup"><span data-stu-id="f1599-106">[out] A pointer to the local variable's slot index.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f1599-107">返回值</span><span class="sxs-lookup"><span data-stu-id="f1599-107">Return Value</span></span>  
 <span data-ttu-id="f1599-108">`S_OK` 如果成功。</span><span class="sxs-lookup"><span data-stu-id="f1599-108">`S_OK` if successful.</span></span> <span data-ttu-id="f1599-109">如果变量是一个函数参数，则为 `E_FAIL`。</span><span class="sxs-lookup"><span data-stu-id="f1599-109">`E_FAIL` if the variable is a function argument.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f1599-110">备注</span><span class="sxs-lookup"><span data-stu-id="f1599-110">Remarks</span></span>  
 <span data-ttu-id="f1599-111">本地变量的托管槽索引可用于检索变量的元数据信息</span><span class="sxs-lookup"><span data-stu-id="f1599-111">The managed slot index of a local variable can be used to retrieve the variable's metadata information</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f1599-112">此方法仅适用于 .NET Native。</span><span class="sxs-lookup"><span data-stu-id="f1599-112">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f1599-113">惠?</span><span class="sxs-lookup"><span data-stu-id="f1599-113">Requirements</span></span>  
 <span data-ttu-id="f1599-114">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="f1599-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f1599-115">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f1599-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f1599-116">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f1599-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f1599-117">**.NET framework 版本：**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f1599-117">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f1599-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="f1599-118">See Also</span></span>  
 [<span data-ttu-id="f1599-119">ICorDebugVariableSymbol 接口</span><span class="sxs-lookup"><span data-stu-id="f1599-119">ICorDebugVariableSymbol Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablesymbol-interface.md)  
 [<span data-ttu-id="f1599-120">调试接口</span><span class="sxs-lookup"><span data-stu-id="f1599-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
