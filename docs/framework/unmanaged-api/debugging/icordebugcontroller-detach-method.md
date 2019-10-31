---
title: ICorDebugController::Detach 方法
ms.date: 03/30/2017
api_name:
- ICorDebugController.Detach
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugController::Detach
helpviewer_keywords:
- Detach method, ICorDebugController interface [.NET Framework debugging]
- ICorDebugController::Detach method [.NET Framework debugging]
ms.assetid: 06fae364-f2c6-4a50-aa7e-3da9f2684dc3
topic_type:
- apiref
ms.openlocfilehash: b98077914d680c908587649fdd517aca9c8dcd40
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73125428"
---
# <a name="icordebugcontrollerdetach-method"></a><span data-ttu-id="c75b9-102">ICorDebugController::Detach 方法</span><span class="sxs-lookup"><span data-stu-id="c75b9-102">ICorDebugController::Detach Method</span></span>
<span data-ttu-id="c75b9-103">将调试器与进程或应用程序域分离。</span><span class="sxs-lookup"><span data-stu-id="c75b9-103">Detaches the debugger from the process or application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c75b9-104">语法</span><span class="sxs-lookup"><span data-stu-id="c75b9-104">Syntax</span></span>  
  
```cpp  
HRESULT Detach ();  
```  
  
## <a name="remarks"></a><span data-ttu-id="c75b9-105">备注</span><span class="sxs-lookup"><span data-stu-id="c75b9-105">Remarks</span></span>  
 <span data-ttu-id="c75b9-106">进程或应用程序域将继续正常执行，但 "ICorDebugProcess" 或 "ICorDebugAppDomain" 对象不再有效，且不会发生进一步的回调。</span><span class="sxs-lookup"><span data-stu-id="c75b9-106">The process or application domain continues execution normally, but the "ICorDebugProcess" or "ICorDebugAppDomain" object is no longer valid and no further callbacks will occur.</span></span>  
  
 <span data-ttu-id="c75b9-107">在 .NET Framework 版本2.0 中，如果启用了非托管调试，则此方法将因操作系统限制而失败。</span><span class="sxs-lookup"><span data-stu-id="c75b9-107">In the .NET Framework version 2.0, if unmanaged debugging is enabled, this method will fail due to operating system limitations.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c75b9-108">要求</span><span class="sxs-lookup"><span data-stu-id="c75b9-108">Requirements</span></span>  
 <span data-ttu-id="c75b9-109">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="c75b9-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c75b9-110">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c75b9-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c75b9-111">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c75b9-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c75b9-112">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c75b9-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c75b9-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="c75b9-113">See also</span></span>
