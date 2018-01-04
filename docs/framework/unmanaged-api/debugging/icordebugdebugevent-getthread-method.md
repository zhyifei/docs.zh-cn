---
title: ICorDebugDebugEvent::GetThread Method
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 4f2e9a2c-8369-4a07-a881-ad5422626353
caps.latest.revision: "5"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: faf1ace6c65f38e9a1d5b958b633c95dbcd3dcf8
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugdebugeventgetthread-method"></a><span data-ttu-id="f6f01-102">ICorDebugDebugEvent::GetThread Method</span><span class="sxs-lookup"><span data-stu-id="f6f01-102">ICorDebugDebugEvent::GetThread Method</span></span>
<span data-ttu-id="f6f01-103">获取发生事件的线程。</span><span class="sxs-lookup"><span data-stu-id="f6f01-103">Gets the thread on which the event occurred.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f6f01-104">语法</span><span class="sxs-lookup"><span data-stu-id="f6f01-104">Syntax</span></span>  
  
```  
HRESULT GetThread(  
        [out]ICorDebugThread **ppThread  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="f6f01-105">参数</span><span class="sxs-lookup"><span data-stu-id="f6f01-105">Parameters</span></span>  
 <span data-ttu-id="f6f01-106">ppThread</span><span class="sxs-lookup"><span data-stu-id="f6f01-106">ppThread</span></span>  
 <span data-ttu-id="f6f01-107">[out]指向一个表示事件发生的线程的 ICorDebugThread 对象的地址的指针。</span><span class="sxs-lookup"><span data-stu-id="f6f01-107">[out] A pointer to the address of an ICorDebugThread object that represents the thread on which the event occurred.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f6f01-108">备注</span><span class="sxs-lookup"><span data-stu-id="f6f01-108">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f6f01-109">此方法仅适用于 .NET Native。</span><span class="sxs-lookup"><span data-stu-id="f6f01-109">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f6f01-110">惠?</span><span class="sxs-lookup"><span data-stu-id="f6f01-110">Requirements</span></span>  
 <span data-ttu-id="f6f01-111">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="f6f01-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f6f01-112">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f6f01-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f6f01-113">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f6f01-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f6f01-114">**.NET framework 版本：**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f6f01-114">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f6f01-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="f6f01-115">See Also</span></span>  
 [<span data-ttu-id="f6f01-116">ICorDebugDebugEvent 接口</span><span class="sxs-lookup"><span data-stu-id="f6f01-116">ICorDebugDebugEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-interface.md)  
 [<span data-ttu-id="f6f01-117">调试接口</span><span class="sxs-lookup"><span data-stu-id="f6f01-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
