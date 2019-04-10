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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7f4794fb0383435f828626497036ad3458df2173
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59204986"
---
# <a name="icordebugmanagedcallbackcontrolctrap-method"></a><span data-ttu-id="c2836-102">ICorDebugManagedCallback::ControlCTrap 方法</span><span class="sxs-lookup"><span data-stu-id="c2836-102">ICorDebugManagedCallback::ControlCTrap Method</span></span>
<span data-ttu-id="c2836-103">通知调试器 CTRL + C 正在调试的进程中捕获。</span><span class="sxs-lookup"><span data-stu-id="c2836-103">Notifies the debugger that a CTRL+C is trapped in the process that is being debugged.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c2836-104">语法</span><span class="sxs-lookup"><span data-stu-id="c2836-104">Syntax</span></span>  
  
```  
HRESULT ControlCTrap (  
    [in] ICorDebugProcess *pProcess  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c2836-105">参数</span><span class="sxs-lookup"><span data-stu-id="c2836-105">Parameters</span></span>  
 `pProcess`  
 <span data-ttu-id="c2836-106">[in]指向表示在其中捕获 CTRL + C 流程 ICorDebugProcess 对象的指针。</span><span class="sxs-lookup"><span data-stu-id="c2836-106">[in] A pointer to an ICorDebugProcess object that represents the process in which the CTRL+C is trapped.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c2836-107">返回值</span><span class="sxs-lookup"><span data-stu-id="c2836-107">Return Value</span></span>  
  
|<span data-ttu-id="c2836-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="c2836-108">HRESULT</span></span>|<span data-ttu-id="c2836-109">描述</span><span class="sxs-lookup"><span data-stu-id="c2836-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="c2836-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="c2836-110">S_OK</span></span>|<span data-ttu-id="c2836-111">调试器将处理 CTRL + C 陷阱。</span><span class="sxs-lookup"><span data-stu-id="c2836-111">The debugger will handle the CTRL+C trap.</span></span>|  
|<span data-ttu-id="c2836-112">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="c2836-112">S_FALSE</span></span>|<span data-ttu-id="c2836-113">调试器不会处理 CTRL + C 陷阱。</span><span class="sxs-lookup"><span data-stu-id="c2836-113">The debugger will not handle the CTRL+C trap.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c2836-114">备注</span><span class="sxs-lookup"><span data-stu-id="c2836-114">Remarks</span></span>  
 <span data-ttu-id="c2836-115">此回调的情况下，进程内的所有应用程序域都已停止。</span><span class="sxs-lookup"><span data-stu-id="c2836-115">All application domains within the process are stopped for this callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c2836-116">要求</span><span class="sxs-lookup"><span data-stu-id="c2836-116">Requirements</span></span>  
 <span data-ttu-id="c2836-117">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="c2836-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c2836-118">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c2836-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c2836-119">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c2836-119">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="c2836-120">.NET Framework 版本：</span><span class="sxs-lookup"><span data-stu-id="c2836-120">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="c2836-121">请参阅</span><span class="sxs-lookup"><span data-stu-id="c2836-121">See also</span></span>

- [<span data-ttu-id="c2836-122">ICorDebugManagedCallback 接口</span><span class="sxs-lookup"><span data-stu-id="c2836-122">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
