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
ms.openlocfilehash: 48bfce9966ff12fe1b425fbcd9a81860628a54e6
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/12/2020
ms.locfileid: "83212667"
---
# <a name="icordebugmanagedcallbacknamechange-method"></a><span data-ttu-id="8b364-102">ICorDebugManagedCallback::NameChange 方法</span><span class="sxs-lookup"><span data-stu-id="8b364-102">ICorDebugManagedCallback::NameChange Method</span></span>
<span data-ttu-id="8b364-103">通知调试器应用程序域或线程的名称已更改。</span><span class="sxs-lookup"><span data-stu-id="8b364-103">Notifies the debugger that the name of either an application domain or a thread has changed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8b364-104">语法</span><span class="sxs-lookup"><span data-stu-id="8b364-104">Syntax</span></span>  
  
```cpp  
HRESULT NameChange (  
    [in] ICorDebugAppDomain *pAppDomain,  
    [in] ICorDebugThread    *pThread  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8b364-105">参数</span><span class="sxs-lookup"><span data-stu-id="8b364-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="8b364-106">中指向 ICorDebugAppDomain 对象的指针，该对象表示具有名称更改或包含名称更改的线程的应用程序域。</span><span class="sxs-lookup"><span data-stu-id="8b364-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain that either had a name change or that contains the thread that had a name change.</span></span>  
  
 `pThread`  
 <span data-ttu-id="8b364-107">中指向 ICorDebugThread 对象的指针，该对象表示名称发生更改的线程。</span><span class="sxs-lookup"><span data-stu-id="8b364-107">[in] A pointer to an ICorDebugThread object that represents the thread that had a name change.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8b364-108">要求</span><span class="sxs-lookup"><span data-stu-id="8b364-108">Requirements</span></span>  
 <span data-ttu-id="8b364-109">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="8b364-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8b364-110">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8b364-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8b364-111">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8b364-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8b364-112">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8b364-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8b364-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="8b364-113">See also</span></span>

- [<span data-ttu-id="8b364-114">ICorDebugManagedCallback 接口</span><span class="sxs-lookup"><span data-stu-id="8b364-114">ICorDebugManagedCallback Interface</span></span>](icordebugmanagedcallback-interface.md)
