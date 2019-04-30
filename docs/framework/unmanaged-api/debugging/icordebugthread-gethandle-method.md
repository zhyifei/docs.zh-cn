---
title: ICorDebugThread::GetHandle 方法
ms.date: 03/30/2017
api_name:
- ICorDebugThread.GetHandle
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread::GetHandle
helpviewer_keywords:
- GetHandle method, ICorDebugThread interface [.NET Framework debugging]
- ICorDebugThread::GetHandle method [.NET Framework debugging]
ms.assetid: 172ef8c4-2ead-4cfc-bd2e-dee4fb7191cd
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 900fece1dd29f73f77b85ff08e4deff1396f8aaf
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61994014"
---
# <a name="icordebugthreadgethandle-method"></a><span data-ttu-id="cd9b6-102">ICorDebugThread::GetHandle 方法</span><span class="sxs-lookup"><span data-stu-id="cd9b6-102">ICorDebugThread::GetHandle Method</span></span>
<span data-ttu-id="cd9b6-103">获取此 ICorDebugThread 的活动部分当前句柄。</span><span class="sxs-lookup"><span data-stu-id="cd9b6-103">Gets the current handle for the active part of this ICorDebugThread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cd9b6-104">语法</span><span class="sxs-lookup"><span data-stu-id="cd9b6-104">Syntax</span></span>  
  
```  
HRESULT GetHandle (  
    [out] HTHREAD *phThreadHandle  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cd9b6-105">参数</span><span class="sxs-lookup"><span data-stu-id="cd9b6-105">Parameters</span></span>  
 `phThreadHandle`  
 <span data-ttu-id="cd9b6-106">[out]此线程的活动部分的句柄 HTHREAD 指向的指针。</span><span class="sxs-lookup"><span data-stu-id="cd9b6-106">[out] A pointer to an HTHREAD that is the handle of the active part of this thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="cd9b6-107">备注</span><span class="sxs-lookup"><span data-stu-id="cd9b6-107">Remarks</span></span>  
 <span data-ttu-id="cd9b6-108">改变该句柄，因为该过程执行，并可能会因线程的不同部分。</span><span class="sxs-lookup"><span data-stu-id="cd9b6-108">The handle may change as the process executes, and may be different for different parts of the thread.</span></span>  
  
 <span data-ttu-id="cd9b6-109">调试 API 由拥有此句柄。</span><span class="sxs-lookup"><span data-stu-id="cd9b6-109">This handle is owned by the debugging API.</span></span> <span data-ttu-id="cd9b6-110">调试程序应使用它之前对其进行复制。</span><span class="sxs-lookup"><span data-stu-id="cd9b6-110">The debugger should duplicate it before using it.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cd9b6-111">要求</span><span class="sxs-lookup"><span data-stu-id="cd9b6-111">Requirements</span></span>  
 <span data-ttu-id="cd9b6-112">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="cd9b6-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cd9b6-113">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="cd9b6-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="cd9b6-114">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="cd9b6-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="cd9b6-115">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cd9b6-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
