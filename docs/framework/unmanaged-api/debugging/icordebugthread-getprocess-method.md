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
ms.openlocfilehash: 8928e22b70af0360660c30289ee999a3e4c5e99e
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73133474"
---
# <a name="icordebugthreadgetprocess-method"></a><span data-ttu-id="c7ee5-102">ICorDebugThread::GetProcess 方法</span><span class="sxs-lookup"><span data-stu-id="c7ee5-102">ICorDebugThread::GetProcess Method</span></span>
<span data-ttu-id="c7ee5-103">获取一个接口指针，该指针指向此 ICorDebugThread 构成部件的进程。</span><span class="sxs-lookup"><span data-stu-id="c7ee5-103">Gets an interface pointer to the process of which this ICorDebugThread forms a part.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c7ee5-104">语法</span><span class="sxs-lookup"><span data-stu-id="c7ee5-104">Syntax</span></span>  
  
```cpp  
HRESULT GetProcess (  
    [out] ICorDebugProcess   **ppProcess  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c7ee5-105">参数</span><span class="sxs-lookup"><span data-stu-id="c7ee5-105">Parameters</span></span>  
 `ppProcess`  
 <span data-ttu-id="c7ee5-106">弄指向表示进程的 ICorDebugProcess 接口对象地址的指针。</span><span class="sxs-lookup"><span data-stu-id="c7ee5-106">[out] A pointer to the address of an ICorDebugProcess interface object that represents the process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c7ee5-107">要求</span><span class="sxs-lookup"><span data-stu-id="c7ee5-107">Requirements</span></span>  
 <span data-ttu-id="c7ee5-108">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="c7ee5-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c7ee5-109">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c7ee5-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c7ee5-110">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c7ee5-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c7ee5-111">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c7ee5-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
