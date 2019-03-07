---
title: ICorDebugProcess::GetThread 方法
ms.date: 03/30/2017
api_name:
- ICorDebugProcess.GetThread
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess::GetThread
helpviewer_keywords:
- ICorDebugProcess::GetThread method [.NET Framework debugging]
- GetThread method, ICorDebugProcess interface [.NET Framework debugging]
ms.assetid: a48261ed-700b-41c9-8cb4-18c526546603
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 36070d5374a11daf4b7800481c86d61057989631
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2019
ms.locfileid: "57470068"
---
# <a name="icordebugprocessgetthread-method"></a><span data-ttu-id="db360-102">ICorDebugProcess::GetThread 方法</span><span class="sxs-lookup"><span data-stu-id="db360-102">ICorDebugProcess::GetThread Method</span></span>
<span data-ttu-id="db360-103">获取具有指定的操作系统 (OS) 线程 id。 此进程的线程</span><span class="sxs-lookup"><span data-stu-id="db360-103">Gets this process's thread that has the specified operating system (OS) thread ID.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="db360-104">语法</span><span class="sxs-lookup"><span data-stu-id="db360-104">Syntax</span></span>  
  
```  
HRESULT GetThread(  
    [in] DWORD dwThreadId,  
    [out] ICorDebugThread **ppThread);  
```  
  
## <a name="parameters"></a><span data-ttu-id="db360-105">参数</span><span class="sxs-lookup"><span data-stu-id="db360-105">Parameters</span></span>  
 `dwThreadId`  
 <span data-ttu-id="db360-106">[in]操作系统线程的线程 ID 来检索。</span><span class="sxs-lookup"><span data-stu-id="db360-106">[in] The OS thread ID of the thread to be retrieved.</span></span>  
  
 `ppThread`  
 <span data-ttu-id="db360-107">[out]指向一个 ICorDebugThread 对象，表示在线程的地址的指针。</span><span class="sxs-lookup"><span data-stu-id="db360-107">[out] A pointer to the address of an ICorDebugThread object that represents the thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="db360-108">要求</span><span class="sxs-lookup"><span data-stu-id="db360-108">Requirements</span></span>  
 <span data-ttu-id="db360-109">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="db360-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="db360-110">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="db360-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="db360-111">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="db360-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="db360-112">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="db360-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
