---
title: ICorDebugManagedCallback::ControlCTrap 方法
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.ControlCTrap
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::ControlCTrap
helpviewer_keywords:
- ICorDebugManagedCallback::ControlCTrap method [.NET Framework debugging]
- ControlCTrap method [.NET Framework debugging]
ms.assetid: 0500854e-2121-43d9-a028-64312da35258
topic_type:
- apiref
ms.openlocfilehash: da35db8a943fda5fb3fbf4126684bb9cb7243001
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73137430"
---
# <a name="icordebugmanagedcallbackcontrolctrap-method"></a><span data-ttu-id="6b7fa-102">ICorDebugManagedCallback::ControlCTrap 方法</span><span class="sxs-lookup"><span data-stu-id="6b7fa-102">ICorDebugManagedCallback::ControlCTrap Method</span></span>
<span data-ttu-id="6b7fa-103">通知调试器在被调试的进程中捕获了 CTRL + C。</span><span class="sxs-lookup"><span data-stu-id="6b7fa-103">Notifies the debugger that a CTRL+C is trapped in the process that is being debugged.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6b7fa-104">语法</span><span class="sxs-lookup"><span data-stu-id="6b7fa-104">Syntax</span></span>  
  
```cpp  
HRESULT ControlCTrap (  
    [in] ICorDebugProcess *pProcess  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6b7fa-105">参数</span><span class="sxs-lookup"><span data-stu-id="6b7fa-105">Parameters</span></span>  
 `pProcess`  
 <span data-ttu-id="6b7fa-106">中指向 ICorDebugProcess 对象的指针，该对象表示在其中捕获 CTRL + C 的进程。</span><span class="sxs-lookup"><span data-stu-id="6b7fa-106">[in] A pointer to an ICorDebugProcess object that represents the process in which the CTRL+C is trapped.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="6b7fa-107">返回值</span><span class="sxs-lookup"><span data-stu-id="6b7fa-107">Return Value</span></span>  
  
|<span data-ttu-id="6b7fa-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="6b7fa-108">HRESULT</span></span>|<span data-ttu-id="6b7fa-109">描述</span><span class="sxs-lookup"><span data-stu-id="6b7fa-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="6b7fa-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="6b7fa-110">S_OK</span></span>|<span data-ttu-id="6b7fa-111">调试器将处理 CTRL + C 陷阱。</span><span class="sxs-lookup"><span data-stu-id="6b7fa-111">The debugger will handle the CTRL+C trap.</span></span>|  
|<span data-ttu-id="6b7fa-112">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="6b7fa-112">S_FALSE</span></span>|<span data-ttu-id="6b7fa-113">调试器将不会处理 CTRL + C 陷阱。</span><span class="sxs-lookup"><span data-stu-id="6b7fa-113">The debugger will not handle the CTRL+C trap.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6b7fa-114">备注</span><span class="sxs-lookup"><span data-stu-id="6b7fa-114">Remarks</span></span>  
 <span data-ttu-id="6b7fa-115">此回调的进程中的所有应用程序域都已停止。</span><span class="sxs-lookup"><span data-stu-id="6b7fa-115">All application domains within the process are stopped for this callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6b7fa-116">要求</span><span class="sxs-lookup"><span data-stu-id="6b7fa-116">Requirements</span></span>  
 <span data-ttu-id="6b7fa-117">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="6b7fa-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6b7fa-118">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6b7fa-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6b7fa-119">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6b7fa-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6b7fa-120">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6b7fa-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6b7fa-121">请参阅</span><span class="sxs-lookup"><span data-stu-id="6b7fa-121">See also</span></span>

- [<span data-ttu-id="6b7fa-122">ICorDebugManagedCallback 接口</span><span class="sxs-lookup"><span data-stu-id="6b7fa-122">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
