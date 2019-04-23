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
ms.openlocfilehash: 85a9bde77f7c393756ec1d3e7d30b96392aa6a94
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59151796"
---
# <a name="icordebugcontrollerdetach-method"></a><span data-ttu-id="8cf86-102">ICorDebugController::Detach 方法</span><span class="sxs-lookup"><span data-stu-id="8cf86-102">ICorDebugController::Detach Method</span></span>
<span data-ttu-id="8cf86-103">从分离调试器进程或应用程序域。</span><span class="sxs-lookup"><span data-stu-id="8cf86-103">Detaches the debugger from the process or application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8cf86-104">语法</span><span class="sxs-lookup"><span data-stu-id="8cf86-104">Syntax</span></span>  
  
```  
HRESULT Detach ();  
```  
  
## <a name="remarks"></a><span data-ttu-id="8cf86-105">备注</span><span class="sxs-lookup"><span data-stu-id="8cf86-105">Remarks</span></span>  
 <span data-ttu-id="8cf86-106">进程或应用程序域将继续执行正常，但"ICorDebugProcess"或"ICorDebugAppDomain"对象不再有效，会进行任何进一步的回调。</span><span class="sxs-lookup"><span data-stu-id="8cf86-106">The process or application domain continues execution normally, but the "ICorDebugProcess" or "ICorDebugAppDomain" object is no longer valid and no further callbacks will occur.</span></span>  
  
 <span data-ttu-id="8cf86-107">在.NET Framework 2.0 版中，如果启用非托管调试，则此方法将失败由于操作系统限制。</span><span class="sxs-lookup"><span data-stu-id="8cf86-107">In the .NET Framework version 2.0, if unmanaged debugging is enabled, this method will fail due to operating system limitations.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8cf86-108">要求</span><span class="sxs-lookup"><span data-stu-id="8cf86-108">Requirements</span></span>  
 <span data-ttu-id="8cf86-109">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="8cf86-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8cf86-110">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8cf86-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8cf86-111">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8cf86-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8cf86-112">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8cf86-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8cf86-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="8cf86-113">See also</span></span>
