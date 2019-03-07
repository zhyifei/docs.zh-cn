---
title: ICorDebugThread::GetProcess 方法
ms.date: 03/30/2017
api_name:
- ICorDebugThread.GetProcess
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread::GetProcess
helpviewer_keywords:
- ICorDebugThread::GetProcess method [.NET Framework debugging]
- GetProcess method, ICorDebugThread interface [.NET Framework debugging]
ms.assetid: 163816e7-0739-4566-b3df-cd256be8b8a4
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 46aa2ec5a282ef56f28d5fa0499571028e6602e6
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2019
ms.locfileid: "57483623"
---
# <a name="icordebugthreadgetprocess-method"></a><span data-ttu-id="570d0-102">ICorDebugThread::GetProcess 方法</span><span class="sxs-lookup"><span data-stu-id="570d0-102">ICorDebugThread::GetProcess Method</span></span>
<span data-ttu-id="570d0-103">获取到此 ICorDebugThread 构成部分的进程的接口指针。</span><span class="sxs-lookup"><span data-stu-id="570d0-103">Gets an interface pointer to the process of which this ICorDebugThread forms a part.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="570d0-104">语法</span><span class="sxs-lookup"><span data-stu-id="570d0-104">Syntax</span></span>  
  
```  
HRESULT GetProcess (  
    [out] ICorDebugProcess   **ppProcess  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="570d0-105">参数</span><span class="sxs-lookup"><span data-stu-id="570d0-105">Parameters</span></span>  
 `ppProcess`  
 <span data-ttu-id="570d0-106">[out]指向表示流程 ICorDebugProcess 接口对象的地址的指针。</span><span class="sxs-lookup"><span data-stu-id="570d0-106">[out] A pointer to the address of an ICorDebugProcess interface object that represents the process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="570d0-107">要求</span><span class="sxs-lookup"><span data-stu-id="570d0-107">Requirements</span></span>  
 <span data-ttu-id="570d0-108">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="570d0-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="570d0-109">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="570d0-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="570d0-110">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="570d0-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="570d0-111">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="570d0-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
