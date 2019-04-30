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
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61987024"
---
# <a name="icordebugthreadgetprocess-method"></a><span data-ttu-id="b03dd-102">ICorDebugThread::GetProcess 方法</span><span class="sxs-lookup"><span data-stu-id="b03dd-102">ICorDebugThread::GetProcess Method</span></span>
<span data-ttu-id="b03dd-103">获取到此 ICorDebugThread 构成部分的进程的接口指针。</span><span class="sxs-lookup"><span data-stu-id="b03dd-103">Gets an interface pointer to the process of which this ICorDebugThread forms a part.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b03dd-104">语法</span><span class="sxs-lookup"><span data-stu-id="b03dd-104">Syntax</span></span>  
  
```  
HRESULT GetProcess (  
    [out] ICorDebugProcess   **ppProcess  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b03dd-105">参数</span><span class="sxs-lookup"><span data-stu-id="b03dd-105">Parameters</span></span>  
 `ppProcess`  
 <span data-ttu-id="b03dd-106">[out]指向表示流程 ICorDebugProcess 接口对象的地址的指针。</span><span class="sxs-lookup"><span data-stu-id="b03dd-106">[out] A pointer to the address of an ICorDebugProcess interface object that represents the process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b03dd-107">要求</span><span class="sxs-lookup"><span data-stu-id="b03dd-107">Requirements</span></span>  
 <span data-ttu-id="b03dd-108">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="b03dd-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b03dd-109">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b03dd-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b03dd-110">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b03dd-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b03dd-111">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b03dd-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
