---
title: "ICorDebugThread3::CreateStackWalk 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugThread3.CreateStackWalk Method
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugThread3::CreateStackWalk
helpviewer_keywords:
- CreateStackWalk method [.NET Framework debugging]
- ICorDebugThread3::CreateStackWalk method [.NET Framework debugging]
ms.assetid: c55e35d9-f9aa-4268-94b5-dce44c61acf2
topic_type: apiref
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 022b60b50c5e38a776b9076fd4faa62a3c373b06
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugthread3createstackwalk-method"></a><span data-ttu-id="ac04a-102">ICorDebugThread3::CreateStackWalk 方法</span><span class="sxs-lookup"><span data-stu-id="ac04a-102">ICorDebugThread3::CreateStackWalk Method</span></span>
<span data-ttu-id="ac04a-103">创建[ICorDebugStackWalk](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md)线程你想要展开其堆栈的对象。</span><span class="sxs-lookup"><span data-stu-id="ac04a-103">Creates an [ICorDebugStackWalk](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md) object for the thread whose stack you want to unwind.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ac04a-104">语法</span><span class="sxs-lookup"><span data-stu-id="ac04a-104">Syntax</span></span>  
  
```  
HRESULT CreateStackWalk([out] ICorDebugStackWalk **ppStackWalk);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ac04a-105">参数</span><span class="sxs-lookup"><span data-stu-id="ac04a-105">Parameters</span></span>  
 `ppStackWalk`  
 <span data-ttu-id="ac04a-106">[out]指向的地址的指针[ICorDebugStackWalk](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md)线程你想要展开其堆栈的对象。</span><span class="sxs-lookup"><span data-stu-id="ac04a-106">[out] A pointer to address of the [ICorDebugStackWalk](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md) object for the thread whose stack you want to unwind.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ac04a-107">返回值</span><span class="sxs-lookup"><span data-stu-id="ac04a-107">Return Value</span></span>  
 <span data-ttu-id="ac04a-108">此方法返回以下特定 HRESULT 以及表示方法失败的 HRESULT 错误。</span><span class="sxs-lookup"><span data-stu-id="ac04a-108">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="ac04a-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="ac04a-109">HRESULT</span></span>|<span data-ttu-id="ac04a-110">描述</span><span class="sxs-lookup"><span data-stu-id="ac04a-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="ac04a-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="ac04a-111">S_OK</span></span>|<span data-ttu-id="ac04a-112">`ICorDebugStackWalk`已成功创建对象。</span><span class="sxs-lookup"><span data-stu-id="ac04a-112">The `ICorDebugStackWalk` object was successfully created.</span></span>|  
|<span data-ttu-id="ac04a-113">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="ac04a-113">E_FAIL</span></span>|<span data-ttu-id="ac04a-114">`ICorDebugStackWalk`不创建对象。</span><span class="sxs-lookup"><span data-stu-id="ac04a-114">The `ICorDebugStackWalk` object was not created.</span></span>|  
  
## <a name="exceptions"></a><span data-ttu-id="ac04a-115">异常</span><span class="sxs-lookup"><span data-stu-id="ac04a-115">Exceptions</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ac04a-116">备注</span><span class="sxs-lookup"><span data-stu-id="ac04a-116">Remarks</span></span>  
 <span data-ttu-id="ac04a-117">如果`CreateStackWalk`方法成功，则返回`ICorDebugStackWalk`对象的上下文设置为线程的当前上下文。</span><span class="sxs-lookup"><span data-stu-id="ac04a-117">If the `CreateStackWalk` method succeeds, the returned `ICorDebugStackWalk` object's context is set to the thread's current context.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ac04a-118">要求</span><span class="sxs-lookup"><span data-stu-id="ac04a-118">Requirements</span></span>  
 <span data-ttu-id="ac04a-119">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="ac04a-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ac04a-120">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ac04a-120">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ac04a-121">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ac04a-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ac04a-122">**.NET framework 版本：**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ac04a-122">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ac04a-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ac04a-123">See Also</span></span>  
 [<span data-ttu-id="ac04a-124">调试接口</span><span class="sxs-lookup"><span data-stu-id="ac04a-124">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="ac04a-125">调试</span><span class="sxs-lookup"><span data-stu-id="ac04a-125">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
