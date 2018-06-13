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
ms.openlocfilehash: 5a7ef478fed697f4152a6348931ddf3b4b4b2885
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33415004"
---
# <a name="icordebugmanagedcallbacknamechange-method"></a><span data-ttu-id="fc50b-102">ICorDebugManagedCallback::NameChange 方法</span><span class="sxs-lookup"><span data-stu-id="fc50b-102">ICorDebugManagedCallback::NameChange Method</span></span>
<span data-ttu-id="fc50b-103">通知调试器的应用程序域或线程的名称已更改。</span><span class="sxs-lookup"><span data-stu-id="fc50b-103">Notifies the debugger that the name of either an application domain or a thread has changed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fc50b-104">语法</span><span class="sxs-lookup"><span data-stu-id="fc50b-104">Syntax</span></span>  
  
```  
HRESULT NameChange (  
    [in] ICorDebugAppDomain *pAppDomain,  
    [in] ICorDebugThread    *pThread  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="fc50b-105">参数</span><span class="sxs-lookup"><span data-stu-id="fc50b-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="fc50b-106">[in]指向一个表示也许上次名称更改或应用程序域的 ICorDebugAppDomain 对象包含已名称更改的线程。</span><span class="sxs-lookup"><span data-stu-id="fc50b-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain that either had a name change or that contains the thread that had a name change.</span></span>  
  
 `pThread`  
 <span data-ttu-id="fc50b-107">[in]指向一个表示已名称更改的线程的 ICorDebugThread 对象的指针。</span><span class="sxs-lookup"><span data-stu-id="fc50b-107">[in] A pointer to an ICorDebugThread object that represents the thread that had a name change.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fc50b-108">要求</span><span class="sxs-lookup"><span data-stu-id="fc50b-108">Requirements</span></span>  
 <span data-ttu-id="fc50b-109">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="fc50b-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fc50b-110">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="fc50b-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="fc50b-111">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fc50b-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fc50b-112">**.NET framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fc50b-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fc50b-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="fc50b-113">See Also</span></span>  
 [<span data-ttu-id="fc50b-114">ICorDebugManagedCallback 接口</span><span class="sxs-lookup"><span data-stu-id="fc50b-114">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
