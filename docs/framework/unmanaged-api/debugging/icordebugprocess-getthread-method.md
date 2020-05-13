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
ms.openlocfilehash: 081852f91f243c4a979e2969220e71bd10c8c56b
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/12/2020
ms.locfileid: "83212875"
---
# <a name="icordebugprocessgetthread-method"></a><span data-ttu-id="0eab2-102">ICorDebugProcess::GetThread 方法</span><span class="sxs-lookup"><span data-stu-id="0eab2-102">ICorDebugProcess::GetThread Method</span></span>
<span data-ttu-id="0eab2-103">获取此进程的线程，该线程具有指定的操作系统（OS）线程 ID。</span><span class="sxs-lookup"><span data-stu-id="0eab2-103">Gets this process's thread that has the specified operating system (OS) thread ID.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0eab2-104">语法</span><span class="sxs-lookup"><span data-stu-id="0eab2-104">Syntax</span></span>  
  
```cpp  
HRESULT GetThread(  
    [in] DWORD dwThreadId,  
    [out] ICorDebugThread **ppThread);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0eab2-105">参数</span><span class="sxs-lookup"><span data-stu-id="0eab2-105">Parameters</span></span>  
 `dwThreadId`  
 <span data-ttu-id="0eab2-106">中要检索的线程的 OS 线程 ID。</span><span class="sxs-lookup"><span data-stu-id="0eab2-106">[in] The OS thread ID of the thread to be retrieved.</span></span>  
  
 `ppThread`  
 <span data-ttu-id="0eab2-107">弄指向表示线程的 ICorDebugThread 对象的地址的指针。</span><span class="sxs-lookup"><span data-stu-id="0eab2-107">[out] A pointer to the address of an ICorDebugThread object that represents the thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0eab2-108">要求</span><span class="sxs-lookup"><span data-stu-id="0eab2-108">Requirements</span></span>  
 <span data-ttu-id="0eab2-109">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="0eab2-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0eab2-110">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0eab2-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0eab2-111">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0eab2-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0eab2-112">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0eab2-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
