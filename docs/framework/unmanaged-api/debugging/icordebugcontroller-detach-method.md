---
title: "ICorDebugController::Detach 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugController.Detach
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugController::Detach
helpviewer_keywords:
- Detach method, ICorDebugController interface [.NET Framework debugging]
- ICorDebugController::Detach method [.NET Framework debugging]
ms.assetid: 06fae364-f2c6-4a50-aa7e-3da9f2684dc3
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 2d8c1df2fd2aa52f9f5e90a27d42f6568686e908
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugcontrollerdetach-method"></a><span data-ttu-id="11b27-102">ICorDebugController::Detach 方法</span><span class="sxs-lookup"><span data-stu-id="11b27-102">ICorDebugController::Detach Method</span></span>
<span data-ttu-id="11b27-103">从分离调试器进程或应用程序域。</span><span class="sxs-lookup"><span data-stu-id="11b27-103">Detaches the debugger from the process or application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="11b27-104">语法</span><span class="sxs-lookup"><span data-stu-id="11b27-104">Syntax</span></span>  
  
```  
HRESULT Detach ();  
```  
  
## <a name="remarks"></a><span data-ttu-id="11b27-105">备注</span><span class="sxs-lookup"><span data-stu-id="11b27-105">Remarks</span></span>  
 <span data-ttu-id="11b27-106">进程或应用程序域将继续执行正常，但"ICorDebugProcess"或"ICorDebugAppDomain"对象将不再有效，且没有进一步的回调会发生。</span><span class="sxs-lookup"><span data-stu-id="11b27-106">The process or application domain continues execution normally, but the "ICorDebugProcess" or "ICorDebugAppDomain" object is no longer valid and no further callbacks will occur.</span></span>  
  
 <span data-ttu-id="11b27-107">在.NET Framework 2.0 版中，如果启用了非托管调试后，此方法将由于操作系统限制失败。</span><span class="sxs-lookup"><span data-stu-id="11b27-107">In the .NET Framework version 2.0, if unmanaged debugging is enabled, this method will fail due to operating system limitations.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="11b27-108">要求</span><span class="sxs-lookup"><span data-stu-id="11b27-108">Requirements</span></span>  
 <span data-ttu-id="11b27-109">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="11b27-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="11b27-110">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="11b27-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="11b27-111">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="11b27-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="11b27-112">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="11b27-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="11b27-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="11b27-113">See Also</span></span>  
 
