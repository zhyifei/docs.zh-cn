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
ms.openlocfilehash: 6bf73a4be40f1fbd8e9d37477907001604e8e4a6
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73128824"
---
# <a name="icordebugprocessgetthread-method"></a><span data-ttu-id="73d02-102">ICorDebugProcess::GetThread 方法</span><span class="sxs-lookup"><span data-stu-id="73d02-102">ICorDebugProcess::GetThread Method</span></span>
<span data-ttu-id="73d02-103">获取此进程的线程，该线程具有指定的操作系统（OS）线程 ID。</span><span class="sxs-lookup"><span data-stu-id="73d02-103">Gets this process's thread that has the specified operating system (OS) thread ID.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="73d02-104">语法</span><span class="sxs-lookup"><span data-stu-id="73d02-104">Syntax</span></span>  
  
```cpp  
HRESULT GetThread(  
    [in] DWORD dwThreadId,  
    [out] ICorDebugThread **ppThread);  
```  
  
## <a name="parameters"></a><span data-ttu-id="73d02-105">参数</span><span class="sxs-lookup"><span data-stu-id="73d02-105">Parameters</span></span>  
 `dwThreadId`  
 <span data-ttu-id="73d02-106">中要检索的线程的 OS 线程 ID。</span><span class="sxs-lookup"><span data-stu-id="73d02-106">[in] The OS thread ID of the thread to be retrieved.</span></span>  
  
 `ppThread`  
 <span data-ttu-id="73d02-107">弄指向表示线程的 ICorDebugThread 对象的地址的指针。</span><span class="sxs-lookup"><span data-stu-id="73d02-107">[out] A pointer to the address of an ICorDebugThread object that represents the thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="73d02-108">要求</span><span class="sxs-lookup"><span data-stu-id="73d02-108">Requirements</span></span>  
 <span data-ttu-id="73d02-109">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="73d02-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="73d02-110">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="73d02-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="73d02-111">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="73d02-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="73d02-112">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="73d02-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
