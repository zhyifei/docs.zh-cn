---
title: ICorDebugEval::GetThread 方法
ms.date: 03/30/2017
api_name:
- ICorDebugEval.GetThread
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEval::GetThread
helpviewer_keywords:
- GetThread method, ICorDebugEval interface [.NET Framework debugging]
- ICorDebugEval::GetThread method [.NET Framework debugging]
ms.assetid: 57163b0d-c8a7-44af-9078-e7a895d29f9a
topic_type:
- apiref
ms.openlocfilehash: b985ada09e0e1914c5e60da61a45398fc6098b33
ms.sourcegitcommit: fff146ba3fd1762c8c432d95c8b877825ae536fc
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/08/2020
ms.locfileid: "82976273"
---
# <a name="icordebugevalgetthread-method"></a><span data-ttu-id="e1c70-102">ICorDebugEval::GetThread 方法</span><span class="sxs-lookup"><span data-stu-id="e1c70-102">ICorDebugEval::GetThread Method</span></span>
<span data-ttu-id="e1c70-103">获取在其中执行或将执行此计算的线程。</span><span class="sxs-lookup"><span data-stu-id="e1c70-103">Gets the thread in which this evaluation is executing or will execute.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e1c70-104">语法</span><span class="sxs-lookup"><span data-stu-id="e1c70-104">Syntax</span></span>  
  
```cpp  
HRESULT GetThread (  
    [out] ICorDebugThread   **ppThread  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e1c70-105">参数</span><span class="sxs-lookup"><span data-stu-id="e1c70-105">Parameters</span></span>  
 `ppThread`  
 <span data-ttu-id="e1c70-106">弄指向表示线程的 ICorDebugThread 对象的地址的指针。</span><span class="sxs-lookup"><span data-stu-id="e1c70-106">[out] A pointer to the address of an ICorDebugThread object that represents the thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e1c70-107">要求</span><span class="sxs-lookup"><span data-stu-id="e1c70-107">Requirements</span></span>  
 <span data-ttu-id="e1c70-108">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="e1c70-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e1c70-109">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e1c70-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e1c70-110">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e1c70-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e1c70-111">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e1c70-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
