---
title: ICorDebugProcess2::ClearUnmanagedBreakpoint 方法
ms.date: 03/30/2017
api_name:
- ICorDebugProcess2.ClearUnmanagedBreakpoint
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess2::ClearUnmanagedBreakpoint
helpviewer_keywords:
- ClearUnmanagedBreakpoint method [.NET Framework debugging]
- ICorDebugProcess2::ClearUnmanagedBreakpoint method [.NET Framework debugging]
ms.assetid: 12ed0fff-7f0e-4d7a-bb70-b3376371f36c
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f4dcfb977f5ca87f2219fd3ed8ef87d16c2defd2
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61948962"
---
# <a name="icordebugprocess2clearunmanagedbreakpoint-method"></a><span data-ttu-id="c70e2-102">ICorDebugProcess2::ClearUnmanagedBreakpoint 方法</span><span class="sxs-lookup"><span data-stu-id="c70e2-102">ICorDebugProcess2::ClearUnmanagedBreakpoint Method</span></span>
<span data-ttu-id="c70e2-103">移除先前设置在给定地址断点。</span><span class="sxs-lookup"><span data-stu-id="c70e2-103">Removes a previously set breakpoint at the given address.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c70e2-104">语法</span><span class="sxs-lookup"><span data-stu-id="c70e2-104">Syntax</span></span>  
  
```  
HRESULT ClearUnmanagedBreakpoint (  
    [in] CORDB_ADDRESS   address  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c70e2-105">参数</span><span class="sxs-lookup"><span data-stu-id="c70e2-105">Parameters</span></span>  
 `address`  
 <span data-ttu-id="c70e2-106">[in]一个`CORDB_ADDRESS`值，该值指定在其中设置断点的地址。</span><span class="sxs-lookup"><span data-stu-id="c70e2-106">[in] A `CORDB_ADDRESS` value that specifies the address at which the breakpoint was set.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c70e2-107">备注</span><span class="sxs-lookup"><span data-stu-id="c70e2-107">Remarks</span></span>  
 <span data-ttu-id="c70e2-108">指定的断点将之前尚未设置到的早期调用[ICorDebugProcess2::SetUnmanagedBreakpoint](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-setunmanagedbreakpoint-method.md)。</span><span class="sxs-lookup"><span data-stu-id="c70e2-108">The specified breakpoint would have been previously set by an earlier call to [ICorDebugProcess2::SetUnmanagedBreakpoint](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-setunmanagedbreakpoint-method.md).</span></span>  
  
 <span data-ttu-id="c70e2-109">`ClearUnmanagedBreakpoint`正在调试的进程正在运行时，可以调用方法。</span><span class="sxs-lookup"><span data-stu-id="c70e2-109">The `ClearUnmanagedBreakpoint` method can be called while the process being debugged is running.</span></span>  
  
 <span data-ttu-id="c70e2-110">`ClearUnmanagedBreakpoint`方法返回了失败代码，如果仅托管模式附加调试器，或指定地址处不存在任何断点。</span><span class="sxs-lookup"><span data-stu-id="c70e2-110">The `ClearUnmanagedBreakpoint` method returns a failure code if the debugger is attached in managed-only mode or if no breakpoint exists at the specified address.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c70e2-111">要求</span><span class="sxs-lookup"><span data-stu-id="c70e2-111">Requirements</span></span>  
 <span data-ttu-id="c70e2-112">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="c70e2-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c70e2-113">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c70e2-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c70e2-114">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c70e2-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c70e2-115">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c70e2-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
