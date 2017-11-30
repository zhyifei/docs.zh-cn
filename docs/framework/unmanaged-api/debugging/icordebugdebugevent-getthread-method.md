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
ms.openlocfilehash: 13b950545c2c8c8b54d24b932351d80280e1dac0
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugdebugeventgetthread-method"></a><span data-ttu-id="9f2c2-102">ICorDebugDebugEvent::GetThread Method</span><span class="sxs-lookup"><span data-stu-id="9f2c2-102">ICorDebugDebugEvent::GetThread Method</span></span>
<span data-ttu-id="9f2c2-103">获取发生事件的线程。</span><span class="sxs-lookup"><span data-stu-id="9f2c2-103">Gets the thread on which the event occurred.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9f2c2-104">语法</span><span class="sxs-lookup"><span data-stu-id="9f2c2-104">Syntax</span></span>  
  
```  
HRESULT GetThread(  
        [out]ICorDebugThread **ppThread  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="9f2c2-105">参数</span><span class="sxs-lookup"><span data-stu-id="9f2c2-105">Parameters</span></span>  
 <span data-ttu-id="9f2c2-106">ppThread</span><span class="sxs-lookup"><span data-stu-id="9f2c2-106">ppThread</span></span>  
 <span data-ttu-id="9f2c2-107">[out]指向一个表示事件发生的线程的 ICorDebugThread 对象的地址的指针。</span><span class="sxs-lookup"><span data-stu-id="9f2c2-107">[out] A pointer to the address of an ICorDebugThread object that represents the thread on which the event occurred.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9f2c2-108">备注</span><span class="sxs-lookup"><span data-stu-id="9f2c2-108">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9f2c2-109">此方法仅适用于 .NET Native。</span><span class="sxs-lookup"><span data-stu-id="9f2c2-109">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9f2c2-110">要求</span><span class="sxs-lookup"><span data-stu-id="9f2c2-110">Requirements</span></span>  
 <span data-ttu-id="9f2c2-111">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="9f2c2-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9f2c2-112">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9f2c2-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9f2c2-113">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9f2c2-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9f2c2-114">**.NET framework 版本：**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9f2c2-114">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9f2c2-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9f2c2-115">See Also</span></span>  
 [<span data-ttu-id="9f2c2-116">Icor 调试调试事件接口</span><span class="sxs-lookup"><span data-stu-id="9f2c2-116">ICorDebugDebugEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-interface.md)  
 [<span data-ttu-id="9f2c2-117">调试接口</span><span class="sxs-lookup"><span data-stu-id="9f2c2-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
