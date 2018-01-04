---
title: "ICorDebugThread::GetProcess 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugThread.GetProcess
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugThread::GetProcess
helpviewer_keywords:
- ICorDebugThread::GetProcess method [.NET Framework debugging]
- GetProcess method, ICorDebugThread interface [.NET Framework debugging]
ms.assetid: 163816e7-0739-4566-b3df-cd256be8b8a4
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 04410024dfe145b7df96dc0f3d8df6fab230f2c8
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugthreadgetprocess-method"></a><span data-ttu-id="cc072-102">ICorDebugThread::GetProcess 方法</span><span class="sxs-lookup"><span data-stu-id="cc072-102">ICorDebugThread::GetProcess Method</span></span>
<span data-ttu-id="cc072-103">获取此 ICorDebugThread 构成一部分的进程的接口指针。</span><span class="sxs-lookup"><span data-stu-id="cc072-103">Gets an interface pointer to the process of which this ICorDebugThread forms a part.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cc072-104">语法</span><span class="sxs-lookup"><span data-stu-id="cc072-104">Syntax</span></span>  
  
```  
HRESULT GetProcess (  
    [out] ICorDebugProcess   **ppProcess  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="cc072-105">参数</span><span class="sxs-lookup"><span data-stu-id="cc072-105">Parameters</span></span>  
 `ppProcess`  
 <span data-ttu-id="cc072-106">[out]ICorDebugProcess 接口对象表示进程的地址指针。</span><span class="sxs-lookup"><span data-stu-id="cc072-106">[out] A pointer to the address of an ICorDebugProcess interface object that represents the process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cc072-107">惠?</span><span class="sxs-lookup"><span data-stu-id="cc072-107">Requirements</span></span>  
 <span data-ttu-id="cc072-108">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="cc072-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cc072-109">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="cc072-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="cc072-110">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="cc072-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="cc072-111">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cc072-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
