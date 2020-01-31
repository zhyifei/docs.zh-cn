---
title: ICorDebugManagedCallback::Breakpoint 方法
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.Breakpoint
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::Breakpoint
helpviewer_keywords:
- ICorDebugManagedCallback::Breakpoint method [.NET Framework debugging]
- Breakpoint method [.NET Framework debugging]
ms.assetid: 60b279b0-a726-46d2-8c53-76986a007ebb
topic_type:
- apiref
ms.openlocfilehash: ac91a9c662a82c5ab870d01cb4b5d87c7af6b6ba
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/28/2020
ms.locfileid: "76782076"
---
# <a name="icordebugmanagedcallbackbreakpoint-method"></a><span data-ttu-id="148ae-102">ICorDebugManagedCallback::Breakpoint 方法</span><span class="sxs-lookup"><span data-stu-id="148ae-102">ICorDebugManagedCallback::Breakpoint Method</span></span>
<span data-ttu-id="148ae-103">遇到断点时，通知调试器。</span><span class="sxs-lookup"><span data-stu-id="148ae-103">Notifies the debugger when a breakpoint is encountered.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="148ae-104">语法</span><span class="sxs-lookup"><span data-stu-id="148ae-104">Syntax</span></span>  
  
```cpp  
HRESULT Breakpoint (  
    [in] ICorDebugAppDomain  *pAppDomain,  
    [in] ICorDebugThread     *pThread,  
    [in] ICorDebugBreakpoint *pBreakpoint  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="148ae-105">参数</span><span class="sxs-lookup"><span data-stu-id="148ae-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="148ae-106">中指向 ICorDebugAppDomain 对象的指针，该对象表示包含断点的应用程序域。</span><span class="sxs-lookup"><span data-stu-id="148ae-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain that contains the breakpoint.</span></span>  
  
 `pThread`  
 <span data-ttu-id="148ae-107">中指向 ICorDebugThread 对象的指针，该对象表示包含断点的线程。</span><span class="sxs-lookup"><span data-stu-id="148ae-107">[in] A pointer to an ICorDebugThread object that represents the thread that contains the breakpoint.</span></span>  
  
 `pBreakpoint`  
 <span data-ttu-id="148ae-108">中指向表示断点的 ICorDebugBreakpoint 对象的指针。</span><span class="sxs-lookup"><span data-stu-id="148ae-108">[in] A pointer to an ICorDebugBreakpoint object that represents the breakpoint.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="148ae-109">需求</span><span class="sxs-lookup"><span data-stu-id="148ae-109">Requirements</span></span>  
 <span data-ttu-id="148ae-110">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="148ae-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="148ae-111">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="148ae-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="148ae-112">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="148ae-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="148ae-113">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="148ae-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="148ae-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="148ae-114">See also</span></span>

- [<span data-ttu-id="148ae-115">ICorDebugManagedCallback 接口</span><span class="sxs-lookup"><span data-stu-id="148ae-115">ICorDebugManagedCallback Interface</span></span>](icordebugmanagedcallback-interface.md)
