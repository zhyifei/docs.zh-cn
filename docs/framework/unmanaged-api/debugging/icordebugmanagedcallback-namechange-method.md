---
title: ICorDebugManagedCallback::NameChange 方法
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.NameChange
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::NameChange
helpviewer_keywords:
- ICorDebugManagedCallback::NameChange method [.NET Framework debugging]
- NameChange method [.NET Framework debugging]
ms.assetid: a7018a0e-880e-4b68-b52a-1cd22c7aad62
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 975353403a82956912fa41047253bb0dbf138502
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61995158"
---
# <a name="icordebugmanagedcallbacknamechange-method"></a><span data-ttu-id="faec2-102">ICorDebugManagedCallback::NameChange 方法</span><span class="sxs-lookup"><span data-stu-id="faec2-102">ICorDebugManagedCallback::NameChange Method</span></span>
<span data-ttu-id="faec2-103">通知调试器的应用程序域或线程名称已更改。</span><span class="sxs-lookup"><span data-stu-id="faec2-103">Notifies the debugger that the name of either an application domain or a thread has changed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="faec2-104">语法</span><span class="sxs-lookup"><span data-stu-id="faec2-104">Syntax</span></span>  
  
```  
HRESULT NameChange (  
    [in] ICorDebugAppDomain *pAppDomain,  
    [in] ICorDebugThread    *pThread  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="faec2-105">参数</span><span class="sxs-lookup"><span data-stu-id="faec2-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="faec2-106">[in]指向 ICorDebugAppDomain 对象表示应用程序域的名称更改或，或者必须包含有名称的更改的线程。</span><span class="sxs-lookup"><span data-stu-id="faec2-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain that either had a name change or that contains the thread that had a name change.</span></span>  
  
 `pThread`  
 <span data-ttu-id="faec2-107">[in]指向表示发生了名称更改的线程的 ICorDebugThread 对象的指针。</span><span class="sxs-lookup"><span data-stu-id="faec2-107">[in] A pointer to an ICorDebugThread object that represents the thread that had a name change.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="faec2-108">要求</span><span class="sxs-lookup"><span data-stu-id="faec2-108">Requirements</span></span>  
 <span data-ttu-id="faec2-109">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="faec2-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="faec2-110">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="faec2-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="faec2-111">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="faec2-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="faec2-112">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="faec2-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="faec2-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="faec2-113">See also</span></span>

- [<span data-ttu-id="faec2-114">ICorDebugManagedCallback 接口</span><span class="sxs-lookup"><span data-stu-id="faec2-114">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
