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
ms.openlocfilehash: 33a68d11a8d17e46533b4f83bbf87aafe171e612
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/12/2020
ms.locfileid: "83212394"
---
# <a name="icordebugmanagedcallbackcontrolctrap-method"></a><span data-ttu-id="dbb9d-102">ICorDebugManagedCallback::ControlCTrap 方法</span><span class="sxs-lookup"><span data-stu-id="dbb9d-102">ICorDebugManagedCallback::ControlCTrap Method</span></span>
<span data-ttu-id="dbb9d-103">通知调试器在被调试的进程中捕获了 CTRL + C。</span><span class="sxs-lookup"><span data-stu-id="dbb9d-103">Notifies the debugger that a CTRL+C is trapped in the process that is being debugged.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dbb9d-104">语法</span><span class="sxs-lookup"><span data-stu-id="dbb9d-104">Syntax</span></span>  
  
```cpp  
HRESULT ControlCTrap (  
    [in] ICorDebugProcess *pProcess  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="dbb9d-105">参数</span><span class="sxs-lookup"><span data-stu-id="dbb9d-105">Parameters</span></span>  
 `pProcess`  
 <span data-ttu-id="dbb9d-106">中指向 ICorDebugProcess 对象的指针，该对象表示在其中捕获 CTRL + C 的进程。</span><span class="sxs-lookup"><span data-stu-id="dbb9d-106">[in] A pointer to an ICorDebugProcess object that represents the process in which the CTRL+C is trapped.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="dbb9d-107">返回值</span><span class="sxs-lookup"><span data-stu-id="dbb9d-107">Return Value</span></span>  
  
|<span data-ttu-id="dbb9d-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="dbb9d-108">HRESULT</span></span>|<span data-ttu-id="dbb9d-109">描述</span><span class="sxs-lookup"><span data-stu-id="dbb9d-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="dbb9d-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="dbb9d-110">S_OK</span></span>|<span data-ttu-id="dbb9d-111">调试器将处理 CTRL + C 陷阱。</span><span class="sxs-lookup"><span data-stu-id="dbb9d-111">The debugger will handle the CTRL+C trap.</span></span>|  
|<span data-ttu-id="dbb9d-112">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="dbb9d-112">S_FALSE</span></span>|<span data-ttu-id="dbb9d-113">调试器将不会处理 CTRL + C 陷阱。</span><span class="sxs-lookup"><span data-stu-id="dbb9d-113">The debugger will not handle the CTRL+C trap.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="dbb9d-114">备注</span><span class="sxs-lookup"><span data-stu-id="dbb9d-114">Remarks</span></span>  
 <span data-ttu-id="dbb9d-115">此回调的进程中的所有应用程序域都已停止。</span><span class="sxs-lookup"><span data-stu-id="dbb9d-115">All application domains within the process are stopped for this callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dbb9d-116">要求</span><span class="sxs-lookup"><span data-stu-id="dbb9d-116">Requirements</span></span>  
 <span data-ttu-id="dbb9d-117">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="dbb9d-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dbb9d-118">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="dbb9d-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="dbb9d-119">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="dbb9d-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="dbb9d-120">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dbb9d-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dbb9d-121">请参阅</span><span class="sxs-lookup"><span data-stu-id="dbb9d-121">See also</span></span>

- [<span data-ttu-id="dbb9d-122">ICorDebugManagedCallback 接口</span><span class="sxs-lookup"><span data-stu-id="dbb9d-122">ICorDebugManagedCallback Interface</span></span>](icordebugmanagedcallback-interface.md)
