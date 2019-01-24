---
title: ICorDebugDebugEvent::GetThread Method
ms.date: 03/30/2017
ms.assetid: 4f2e9a2c-8369-4a07-a881-ad5422626353
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 51d674159b33cad1a77a82e39b9f11a38c98cbd3
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54687396"
---
# <a name="icordebugdebugeventgetthread-method"></a><span data-ttu-id="18206-102">ICorDebugDebugEvent::GetThread Method</span><span class="sxs-lookup"><span data-stu-id="18206-102">ICorDebugDebugEvent::GetThread Method</span></span>
<span data-ttu-id="18206-103">获取发生事件的线程。</span><span class="sxs-lookup"><span data-stu-id="18206-103">Gets the thread on which the event occurred.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="18206-104">语法</span><span class="sxs-lookup"><span data-stu-id="18206-104">Syntax</span></span>  
  
```  
HRESULT GetThread(  
        [out]ICorDebugThread **ppThread  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="18206-105">参数</span><span class="sxs-lookup"><span data-stu-id="18206-105">Parameters</span></span>  
 <span data-ttu-id="18206-106">ppThread</span><span class="sxs-lookup"><span data-stu-id="18206-106">ppThread</span></span>  
 <span data-ttu-id="18206-107">[out]指向一个 ICorDebugThread 对象，表示发生事件的线程的地址的指针。</span><span class="sxs-lookup"><span data-stu-id="18206-107">[out] A pointer to the address of an ICorDebugThread object that represents the thread on which the event occurred.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="18206-108">备注</span><span class="sxs-lookup"><span data-stu-id="18206-108">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="18206-109">此方法仅适用于 .NET Native。</span><span class="sxs-lookup"><span data-stu-id="18206-109">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="18206-110">要求</span><span class="sxs-lookup"><span data-stu-id="18206-110">Requirements</span></span>  
 <span data-ttu-id="18206-111">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="18206-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="18206-112">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="18206-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="18206-113">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="18206-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="18206-114">**.NET Framework 版本：**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="18206-114">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="18206-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="18206-115">See also</span></span>
- [<span data-ttu-id="18206-116">ICorDebugDebugEvent 接口</span><span class="sxs-lookup"><span data-stu-id="18206-116">ICorDebugDebugEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-interface.md)
- [<span data-ttu-id="18206-117">调试接口</span><span class="sxs-lookup"><span data-stu-id="18206-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
