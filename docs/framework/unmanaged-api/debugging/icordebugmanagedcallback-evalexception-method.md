---
title: ICorDebugManagedCallback::EvalException 方法
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.EvalException
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::EvalException
helpviewer_keywords:
- EvalException method [.NET Framework debugging]
- ICorDebugManagedCallback::EvalException method [.NET Framework debugging]
ms.assetid: d6036345-18a3-45c1-a302-b1c6f2dced9b
topic_type:
- apiref
ms.openlocfilehash: 20a841006d51671a491e11c4e40287baf739d191
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/12/2020
ms.locfileid: "83209820"
---
# <a name="icordebugmanagedcallbackevalexception-method"></a><span data-ttu-id="c7907-102">ICorDebugManagedCallback::EvalException 方法</span><span class="sxs-lookup"><span data-stu-id="c7907-102">ICorDebugManagedCallback::EvalException Method</span></span>
<span data-ttu-id="c7907-103">通知调试器，计算已终止，并出现未经处理的异常。</span><span class="sxs-lookup"><span data-stu-id="c7907-103">Notifies the debugger that an evaluation has terminated with an unhandled exception.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c7907-104">语法</span><span class="sxs-lookup"><span data-stu-id="c7907-104">Syntax</span></span>  
  
```cpp  
HRESULT EvalException (  
    [in] ICorDebugAppDomain *pAppDomain,  
    [in] ICorDebugThread    *pThread,  
    [in] ICorDebugEval      *pEval  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c7907-105">参数</span><span class="sxs-lookup"><span data-stu-id="c7907-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="c7907-106">中指向 ICorDebugAppDomain 对象的指针，该对象表示评估终止的应用程序域。</span><span class="sxs-lookup"><span data-stu-id="c7907-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain in which the evaluation terminated.</span></span>  
  
 `pThread`  
 <span data-ttu-id="c7907-107">中指向 ICorDebugThread 对象的指针，该对象表示在其中终止计算的线程。</span><span class="sxs-lookup"><span data-stu-id="c7907-107">[in] A pointer to an ICorDebugThread object that represents the thread in which the evaluation terminated.</span></span>  
  
 `pEval`  
 <span data-ttu-id="c7907-108">中指向 ICorDebugEval 对象的指针，该对象表示执行计算的代码。</span><span class="sxs-lookup"><span data-stu-id="c7907-108">[in] A pointer to an ICorDebugEval object that represents the code that performed the evaluation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c7907-109">要求</span><span class="sxs-lookup"><span data-stu-id="c7907-109">Requirements</span></span>  
 <span data-ttu-id="c7907-110">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="c7907-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c7907-111">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c7907-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c7907-112">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c7907-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c7907-113">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c7907-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c7907-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="c7907-114">See also</span></span>

- [<span data-ttu-id="c7907-115">ICorDebugManagedCallback 接口</span><span class="sxs-lookup"><span data-stu-id="c7907-115">ICorDebugManagedCallback Interface</span></span>](icordebugmanagedcallback-interface.md)
