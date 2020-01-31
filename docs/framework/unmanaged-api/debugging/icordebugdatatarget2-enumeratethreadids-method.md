---
title: ICorDebugDataTarget2::EnumerateThreadIDs 方法
ms.date: 03/30/2017
ms.assetid: af02460f-2a45-496e-bc4e-a1ac4f80fe11
ms.openlocfilehash: 74d4905f2b386f8e0345e4300dd2c8c6d0c882ea
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/28/2020
ms.locfileid: "76783641"
---
# <a name="icordebugdatatarget2enumeratethreadids-method"></a><span data-ttu-id="a05d1-102">ICorDebugDataTarget2::EnumerateThreadIDs 方法</span><span class="sxs-lookup"><span data-stu-id="a05d1-102">ICorDebugDataTarget2::EnumerateThreadIDs Method</span></span>
<span data-ttu-id="a05d1-103">返回一组活动线程 ID。</span><span class="sxs-lookup"><span data-stu-id="a05d1-103">Returns a list of active thread IDs.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a05d1-104">语法</span><span class="sxs-lookup"><span data-stu-id="a05d1-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumerateThreadIDs(  
    [in] ULONG32 cThreadIds,   
    [out] ULONG32 *pcThreadIds,   
    [out, size_is(cThreadIds), length_is(*pcThreadIds)] ULONG32 pThreadIds[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a05d1-105">参数</span><span class="sxs-lookup"><span data-stu-id="a05d1-105">Parameters</span></span>  
 <span data-ttu-id="a05d1-106">cThreadID</span><span class="sxs-lookup"><span data-stu-id="a05d1-106">cThreadIDs</span></span>  
 <span data-ttu-id="a05d1-107">[输入] 线程 ID 可返回的上限数。</span><span class="sxs-lookup"><span data-stu-id="a05d1-107">[in] The maximum number of threads whose IDs can be returned.</span></span>  
  
 <span data-ttu-id="a05d1-108">pcThreadID</span><span class="sxs-lookup"><span data-stu-id="a05d1-108">pcThreadIds</span></span>  
 <span data-ttu-id="a05d1-109">[输出] `ULONG32` 指针显示写入 `pThreadIds` 阵列的线程 ID 的实际数目。</span><span class="sxs-lookup"><span data-stu-id="a05d1-109">[out] A pointer to a `ULONG32` that indicates the actual number of thread IDs written to the `pThreadIds` array.</span></span>  
  
 <span data-ttu-id="a05d1-110">pThreadID</span><span class="sxs-lookup"><span data-stu-id="a05d1-110">pThreadIDs</span></span>  
 <span data-ttu-id="a05d1-111">一组线程标识符。</span><span class="sxs-lookup"><span data-stu-id="a05d1-111">An array of thread identifiers.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a05d1-112">备注</span><span class="sxs-lookup"><span data-stu-id="a05d1-112">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="a05d1-113">此方法仅适用于 .NET Native。</span><span class="sxs-lookup"><span data-stu-id="a05d1-113">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a05d1-114">需求</span><span class="sxs-lookup"><span data-stu-id="a05d1-114">Requirements</span></span>  
 <span data-ttu-id="a05d1-115">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。**标头：** Cordebug.idl，Cordebug.idl</span><span class="sxs-lookup"><span data-stu-id="a05d1-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a05d1-116">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a05d1-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a05d1-117">**.NET Framework 版本：** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a05d1-117">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a05d1-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a05d1-118">See also</span></span>

- [<span data-ttu-id="a05d1-119">ICorDebugDataTarget2 接口</span><span class="sxs-lookup"><span data-stu-id="a05d1-119">ICorDebugDataTarget2 Interface</span></span>](icordebugdatatarget2-interface.md)
- [<span data-ttu-id="a05d1-120">调试接口</span><span class="sxs-lookup"><span data-stu-id="a05d1-120">Debugging Interfaces</span></span>](debugging-interfaces.md)
