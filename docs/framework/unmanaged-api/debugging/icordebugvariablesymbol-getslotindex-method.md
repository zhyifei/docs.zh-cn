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
ms.openlocfilehash: d632bc792152afcfc94b51235dc0699fb3efc245
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugvariablesymbolgetslotindex-method"></a><span data-ttu-id="df42c-102">ICorDebugVariableSymbol::GetSlotIndex 方法</span><span class="sxs-lookup"><span data-stu-id="df42c-102">ICorDebugVariableSymbol::GetSlotIndex Method</span></span>
<span data-ttu-id="df42c-103">获取本地变量的托管槽索引。</span><span class="sxs-lookup"><span data-stu-id="df42c-103">Gets the managed slot index of a local variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="df42c-104">语法</span><span class="sxs-lookup"><span data-stu-id="df42c-104">Syntax</span></span>  
  
```  
HRESULT GetSlotIndex(  
   [out] ULONG32 *pSlotIndex  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="df42c-105">参数</span><span class="sxs-lookup"><span data-stu-id="df42c-105">Parameters</span></span>  
 `pSlotIndex`  
 <span data-ttu-id="df42c-106">[out] 指向本地变量的槽索引的指针。</span><span class="sxs-lookup"><span data-stu-id="df42c-106">[out] A pointer to the local variable's slot index.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="df42c-107">返回值</span><span class="sxs-lookup"><span data-stu-id="df42c-107">Return Value</span></span>  
 <span data-ttu-id="df42c-108">`S_OK` 如果成功。</span><span class="sxs-lookup"><span data-stu-id="df42c-108">`S_OK` if successful.</span></span> <span data-ttu-id="df42c-109">如果变量是一个函数参数，则为 `E_FAIL`。</span><span class="sxs-lookup"><span data-stu-id="df42c-109">`E_FAIL` if the variable is a function argument.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="df42c-110">备注</span><span class="sxs-lookup"><span data-stu-id="df42c-110">Remarks</span></span>  
 <span data-ttu-id="df42c-111">本地变量的托管槽索引可用于检索变量的元数据信息</span><span class="sxs-lookup"><span data-stu-id="df42c-111">The managed slot index of a local variable can be used to retrieve the variable's metadata information</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="df42c-112">此方法仅适用于 .NET Native。</span><span class="sxs-lookup"><span data-stu-id="df42c-112">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="df42c-113">要求</span><span class="sxs-lookup"><span data-stu-id="df42c-113">Requirements</span></span>  
 <span data-ttu-id="df42c-114">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="df42c-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="df42c-115">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="df42c-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="df42c-116">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="df42c-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="df42c-117">**.NET framework 版本：**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="df42c-117">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="df42c-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="df42c-118">See Also</span></span>  
 [<span data-ttu-id="df42c-119">ICorDebugVariableSymbol 接口</span><span class="sxs-lookup"><span data-stu-id="df42c-119">ICorDebugVariableSymbol Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablesymbol-interface.md)  
 [<span data-ttu-id="df42c-120">调试接口</span><span class="sxs-lookup"><span data-stu-id="df42c-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
