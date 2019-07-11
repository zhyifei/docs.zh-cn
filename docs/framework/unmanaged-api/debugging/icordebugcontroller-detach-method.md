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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f687e48413cb227ad715720e24bd645065309553
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/10/2019
ms.locfileid: "67748841"
---
# <a name="icordebugcontrollerdetach-method"></a><span data-ttu-id="8e92c-102">ICorDebugController::Detach 方法</span><span class="sxs-lookup"><span data-stu-id="8e92c-102">ICorDebugController::Detach Method</span></span>
<span data-ttu-id="8e92c-103">从分离调试器进程或应用程序域。</span><span class="sxs-lookup"><span data-stu-id="8e92c-103">Detaches the debugger from the process or application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8e92c-104">语法</span><span class="sxs-lookup"><span data-stu-id="8e92c-104">Syntax</span></span>  
  
```cpp  
HRESULT Detach ();  
```  
  
## <a name="remarks"></a><span data-ttu-id="8e92c-105">备注</span><span class="sxs-lookup"><span data-stu-id="8e92c-105">Remarks</span></span>  
 <span data-ttu-id="8e92c-106">进程或应用程序域将继续执行正常，但"ICorDebugProcess"或"ICorDebugAppDomain"对象不再有效，会进行任何进一步的回调。</span><span class="sxs-lookup"><span data-stu-id="8e92c-106">The process or application domain continues execution normally, but the "ICorDebugProcess" or "ICorDebugAppDomain" object is no longer valid and no further callbacks will occur.</span></span>  
  
 <span data-ttu-id="8e92c-107">在.NET Framework 2.0 版中，如果启用非托管调试，则此方法将失败由于操作系统限制。</span><span class="sxs-lookup"><span data-stu-id="8e92c-107">In the .NET Framework version 2.0, if unmanaged debugging is enabled, this method will fail due to operating system limitations.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8e92c-108">要求</span><span class="sxs-lookup"><span data-stu-id="8e92c-108">Requirements</span></span>  
 <span data-ttu-id="8e92c-109">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="8e92c-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8e92c-110">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8e92c-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8e92c-111">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8e92c-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8e92c-112">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8e92c-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8e92c-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="8e92c-113">See also</span></span>
