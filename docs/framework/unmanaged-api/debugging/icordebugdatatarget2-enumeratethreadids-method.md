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
ms.workload: dotnet
ms.openlocfilehash: 9030f7f8453de98f535cf8212e55c7daee94e8e1
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugdatatarget2enumeratethreadids-method"></a><span data-ttu-id="cb861-102">ICorDebugDataTarget2::EnumerateThreadIDs 方法</span><span class="sxs-lookup"><span data-stu-id="cb861-102">ICorDebugDataTarget2::EnumerateThreadIDs Method</span></span>
<span data-ttu-id="cb861-103">返回一组活动线程 ID。</span><span class="sxs-lookup"><span data-stu-id="cb861-103">Returns a list of active thread IDs.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cb861-104">语法</span><span class="sxs-lookup"><span data-stu-id="cb861-104">Syntax</span></span>  
  
```  
HRESULT EnumerateThreadIDs(  
    [in] ULONG32 cThreadIds,   
    [out] ULONG32 *pcThreadIds,   
    [out, size_is(cThreadIds), length_is(*pcThreadIds)] ULONG32 pThreadIds[]  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="cb861-105">参数</span><span class="sxs-lookup"><span data-stu-id="cb861-105">Parameters</span></span>  
 <span data-ttu-id="cb861-106">cThreadID</span><span class="sxs-lookup"><span data-stu-id="cb861-106">cThreadIDs</span></span>  
 <span data-ttu-id="cb861-107">[输入] 线程 ID 可返回的上限数。</span><span class="sxs-lookup"><span data-stu-id="cb861-107">[in] The maximum number of threads whose IDs can be returned.</span></span>  
  
 <span data-ttu-id="cb861-108">pcThreadID</span><span class="sxs-lookup"><span data-stu-id="cb861-108">pcThreadIds</span></span>  
 <span data-ttu-id="cb861-109">[输出] `ULONG32` 指针显示写入 `pThreadIds` 阵列的线程 ID 的实际数目。</span><span class="sxs-lookup"><span data-stu-id="cb861-109">[out] A pointer to a `ULONG32` that indicates the actual number of thread IDs written to the `pThreadIds` array.</span></span>  
  
 <span data-ttu-id="cb861-110">pThreadID</span><span class="sxs-lookup"><span data-stu-id="cb861-110">pThreadIDs</span></span>  
 <span data-ttu-id="cb861-111">一组线程标识符。</span><span class="sxs-lookup"><span data-stu-id="cb861-111">An array of thread identifiers.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="cb861-112">备注</span><span class="sxs-lookup"><span data-stu-id="cb861-112">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="cb861-113">此方法仅适用于 .NET Native。</span><span class="sxs-lookup"><span data-stu-id="cb861-113">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cb861-114">惠?</span><span class="sxs-lookup"><span data-stu-id="cb861-114">Requirements</span></span>  
 <span data-ttu-id="cb861-115">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="cb861-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="cb861-116">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="cb861-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="cb861-117">**.NET framework 版本：**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cb861-117">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cb861-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="cb861-118">See Also</span></span>  
 [<span data-ttu-id="cb861-119">ICorDebugDataTarget2 接口</span><span class="sxs-lookup"><span data-stu-id="cb861-119">ICorDebugDataTarget2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget2-interface.md)  
 [<span data-ttu-id="cb861-120">调试接口</span><span class="sxs-lookup"><span data-stu-id="cb861-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
