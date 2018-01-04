---
title: "ICorDebugProcess::GetThread 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugProcess.GetThread
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugProcess::GetThread
helpviewer_keywords:
- ICorDebugProcess::GetThread method [.NET Framework debugging]
- GetThread method, ICorDebugProcess interface [.NET Framework debugging]
ms.assetid: a48261ed-700b-41c9-8cb4-18c526546603
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 996003f254c5150dfd39ca62d7cadf07282596c9
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugprocessgetthread-method"></a><span data-ttu-id="54728-102">ICorDebugProcess::GetThread 方法</span><span class="sxs-lookup"><span data-stu-id="54728-102">ICorDebugProcess::GetThread Method</span></span>
<span data-ttu-id="54728-103">获取此进程的线程。 具有指定的操作系统 (OS) 线程 id。</span><span class="sxs-lookup"><span data-stu-id="54728-103">Gets this process's thread that has the specified operating system (OS) thread ID.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="54728-104">语法</span><span class="sxs-lookup"><span data-stu-id="54728-104">Syntax</span></span>  
  
```  
HRESULT GetThread(  
    [in] DWORD dwThreadId,  
    [out] ICorDebugThread **ppThread);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="54728-105">参数</span><span class="sxs-lookup"><span data-stu-id="54728-105">Parameters</span></span>  
 `dwThreadId`  
 <span data-ttu-id="54728-106">[in]操作系统线程的线程 ID 来检索。</span><span class="sxs-lookup"><span data-stu-id="54728-106">[in] The OS thread ID of the thread to be retrieved.</span></span>  
  
 `ppThread`  
 <span data-ttu-id="54728-107">[out]指向一个 ICorDebugThread 对象，表示线程的地址的指针。</span><span class="sxs-lookup"><span data-stu-id="54728-107">[out] A pointer to the address of an ICorDebugThread object that represents the thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="54728-108">惠?</span><span class="sxs-lookup"><span data-stu-id="54728-108">Requirements</span></span>  
 <span data-ttu-id="54728-109">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="54728-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="54728-110">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="54728-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="54728-111">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="54728-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="54728-112">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="54728-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
