---
title: ICorDebugDataTarget2::EnumerateThreadIDs 方法
ms.date: 03/30/2017
ms.assetid: af02460f-2a45-496e-bc4e-a1ac4f80fe11
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 70b3b57b51faed51aa7d5a70a3b785e0f719321b
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59215834"
---
# <a name="icordebugdatatarget2enumeratethreadids-method"></a><span data-ttu-id="fcda9-102">ICorDebugDataTarget2::EnumerateThreadIDs 方法</span><span class="sxs-lookup"><span data-stu-id="fcda9-102">ICorDebugDataTarget2::EnumerateThreadIDs Method</span></span>
<span data-ttu-id="fcda9-103">返回一组活动线程 ID。</span><span class="sxs-lookup"><span data-stu-id="fcda9-103">Returns a list of active thread IDs.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fcda9-104">语法</span><span class="sxs-lookup"><span data-stu-id="fcda9-104">Syntax</span></span>  
  
```  
HRESULT EnumerateThreadIDs(  
    [in] ULONG32 cThreadIds,   
    [out] ULONG32 *pcThreadIds,   
    [out, size_is(cThreadIds), length_is(*pcThreadIds)] ULONG32 pThreadIds[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fcda9-105">参数</span><span class="sxs-lookup"><span data-stu-id="fcda9-105">Parameters</span></span>  
 <span data-ttu-id="fcda9-106">cThreadID</span><span class="sxs-lookup"><span data-stu-id="fcda9-106">cThreadIDs</span></span>  
 <span data-ttu-id="fcda9-107">[输入] 线程 ID 可返回的上限数。</span><span class="sxs-lookup"><span data-stu-id="fcda9-107">[in] The maximum number of threads whose IDs can be returned.</span></span>  
  
 <span data-ttu-id="fcda9-108">pcThreadID</span><span class="sxs-lookup"><span data-stu-id="fcda9-108">pcThreadIds</span></span>  
 <span data-ttu-id="fcda9-109">[输出] `ULONG32` 指针显示写入 `pThreadIds` 数组的线程 ID 的实际数目。</span><span class="sxs-lookup"><span data-stu-id="fcda9-109">[out] A pointer to a `ULONG32` that indicates the actual number of thread IDs written to the `pThreadIds` array.</span></span>  
  
 <span data-ttu-id="fcda9-110">pThreadID</span><span class="sxs-lookup"><span data-stu-id="fcda9-110">pThreadIDs</span></span>  
 <span data-ttu-id="fcda9-111">一组线程标识符。</span><span class="sxs-lookup"><span data-stu-id="fcda9-111">An array of thread identifiers.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fcda9-112">备注</span><span class="sxs-lookup"><span data-stu-id="fcda9-112">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="fcda9-113">此方法仅适用于 .NET Native。</span><span class="sxs-lookup"><span data-stu-id="fcda9-113">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fcda9-114">要求</span><span class="sxs-lookup"><span data-stu-id="fcda9-114">Requirements</span></span>  
 <span data-ttu-id="fcda9-115">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="fcda9-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="fcda9-116">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fcda9-116">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="fcda9-117">.NET Framework 版本：</span><span class="sxs-lookup"><span data-stu-id="fcda9-117">.NET Framework Versions:</span></span>** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="fcda9-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="fcda9-118">See also</span></span>

- [<span data-ttu-id="fcda9-119">“ICor调试数据目标2”接口</span><span class="sxs-lookup"><span data-stu-id="fcda9-119">ICorDebugDataTarget2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget2-interface.md)
- [<span data-ttu-id="fcda9-120">调试接口</span><span class="sxs-lookup"><span data-stu-id="fcda9-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
