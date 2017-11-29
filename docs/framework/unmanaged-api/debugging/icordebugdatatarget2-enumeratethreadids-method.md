---
title: "ICorDebugDataTarget2::EnumerateThreadIDs 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: af02460f-2a45-496e-bc4e-a1ac4f80fe11
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: c20b7dd1bcbc27edb9be11419b7919250301d488
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugdatatarget2enumeratethreadids-method"></a><span data-ttu-id="0226b-102">ICorDebugDataTarget2::EnumerateThreadIDs 方法</span><span class="sxs-lookup"><span data-stu-id="0226b-102">ICorDebugDataTarget2::EnumerateThreadIDs Method</span></span>
<span data-ttu-id="0226b-103">返回一组活动线程 ID。</span><span class="sxs-lookup"><span data-stu-id="0226b-103">Returns a list of active thread IDs.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0226b-104">语法</span><span class="sxs-lookup"><span data-stu-id="0226b-104">Syntax</span></span>  
  
```  
HRESULT EnumerateThreadIDs(  
    [in] ULONG32 cThreadIds,   
    [out] ULONG32 *pcThreadIds,   
    [out, size_is(cThreadIds), length_is(*pcThreadIds)] ULONG32 pThreadIds[]  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="0226b-105">参数</span><span class="sxs-lookup"><span data-stu-id="0226b-105">Parameters</span></span>  
 <span data-ttu-id="0226b-106">cThreadID</span><span class="sxs-lookup"><span data-stu-id="0226b-106">cThreadIDs</span></span>  
 <span data-ttu-id="0226b-107">[输入] 线程 ID 可返回的上限数。</span><span class="sxs-lookup"><span data-stu-id="0226b-107">[in] The maximum number of threads whose IDs can be returned.</span></span>  
  
 <span data-ttu-id="0226b-108">pcThreadID</span><span class="sxs-lookup"><span data-stu-id="0226b-108">pcThreadIds</span></span>  
 <span data-ttu-id="0226b-109">[输出] `ULONG32` 指针显示写入 `pThreadIds` 阵列的线程 ID 的实际数目。</span><span class="sxs-lookup"><span data-stu-id="0226b-109">[out] A pointer to a `ULONG32` that indicates the actual number of thread IDs written to the `pThreadIds` array.</span></span>  
  
 <span data-ttu-id="0226b-110">pThreadID</span><span class="sxs-lookup"><span data-stu-id="0226b-110">pThreadIDs</span></span>  
 <span data-ttu-id="0226b-111">一组线程标识符。</span><span class="sxs-lookup"><span data-stu-id="0226b-111">An array of thread identifiers.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0226b-112">备注</span><span class="sxs-lookup"><span data-stu-id="0226b-112">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0226b-113">此方法仅适用于 .NET Native。</span><span class="sxs-lookup"><span data-stu-id="0226b-113">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0226b-114">要求</span><span class="sxs-lookup"><span data-stu-id="0226b-114">Requirements</span></span>  
 <span data-ttu-id="0226b-115">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0226b-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0226b-116">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0226b-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0226b-117">**.NET framework 版本：**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0226b-117">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0226b-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0226b-118">See Also</span></span>  
 [<span data-ttu-id="0226b-119">ICorDebugDataTarget2 接口</span><span class="sxs-lookup"><span data-stu-id="0226b-119">ICorDebugDataTarget2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget2-interface.md)  
 [<span data-ttu-id="0226b-120">调试接口</span><span class="sxs-lookup"><span data-stu-id="0226b-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
