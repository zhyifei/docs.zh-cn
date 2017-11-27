---
title: "ICorDebugEval::GetThread 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugEval.GetThread
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugEval::GetThread
helpviewer_keywords:
- GetThread method, ICorDebugEval interface [.NET Framework debugging]
- ICorDebugEval::GetThread method [.NET Framework debugging]
ms.assetid: 57163b0d-c8a7-44af-9078-e7a895d29f9a
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: cde844d0664f7dc7643ef60b65befa95f2d039e5
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugevalgetthread-method"></a><span data-ttu-id="c694a-102">ICorDebugEval::GetThread 方法</span><span class="sxs-lookup"><span data-stu-id="c694a-102">ICorDebugEval::GetThread Method</span></span>
<span data-ttu-id="c694a-103">获取在其中此评估正在执行，或将执行的线程。</span><span class="sxs-lookup"><span data-stu-id="c694a-103">Gets the thread in which this evaluation is executing or will execute.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c694a-104">语法</span><span class="sxs-lookup"><span data-stu-id="c694a-104">Syntax</span></span>  
  
```  
HRESULT GetThread (  
    [out] ICorDebugThread   **ppThread  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c694a-105">参数</span><span class="sxs-lookup"><span data-stu-id="c694a-105">Parameters</span></span>  
 `ppThread`  
 <span data-ttu-id="c694a-106">[out]指向一个 ICorDebugThread 对象，表示线程的地址的指针。</span><span class="sxs-lookup"><span data-stu-id="c694a-106">[out] A pointer to the address of an ICorDebugThread object that represents the thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c694a-107">要求</span><span class="sxs-lookup"><span data-stu-id="c694a-107">Requirements</span></span>  
 <span data-ttu-id="c694a-108">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="c694a-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c694a-109">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c694a-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c694a-110">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c694a-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c694a-111">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c694a-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
