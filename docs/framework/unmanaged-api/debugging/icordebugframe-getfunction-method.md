---
title: ICorDebugFrame::GetFunction 方法
ms.date: 03/30/2017
api_name:
- ICorDebugFrame.GetFunction
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFrame::GetFunction
helpviewer_keywords:
- GetFunction method, ICorDebugFrame interface [.NET Framework debugging]
- ICorDebugFrame::GetFunction method [.NET Framework debugging]
ms.assetid: 879d2311-0ff1-4616-a8b3-959ea5868b2e
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a48396f8ef668cfe7755b2718180317b465793b6
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2019
ms.locfileid: "57475276"
---
# <a name="icordebugframegetfunction-method"></a><span data-ttu-id="d207d-102">ICorDebugFrame::GetFunction 方法</span><span class="sxs-lookup"><span data-stu-id="d207d-102">ICorDebugFrame::GetFunction Method</span></span>
<span data-ttu-id="d207d-103">获取包含与此堆栈帧关联的代码的函数。</span><span class="sxs-lookup"><span data-stu-id="d207d-103">Gets the function that contains the code associated with this stack frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d207d-104">语法</span><span class="sxs-lookup"><span data-stu-id="d207d-104">Syntax</span></span>  
  
```  
HRESULT GetFunction (  
    [out] ICorDebugFunction  **ppFunction  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d207d-105">参数</span><span class="sxs-lookup"><span data-stu-id="d207d-105">Parameters</span></span>  
 `ppFunction`  
 <span data-ttu-id="d207d-106">[out]指向一个 ICorDebugFunction 对象，表示包含与此堆栈帧关联的代码的函数的地址的指针。</span><span class="sxs-lookup"><span data-stu-id="d207d-106">[out] A pointer to the address of an ICorDebugFunction object that represents the function containing the code associated with this stack frame.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d207d-107">备注</span><span class="sxs-lookup"><span data-stu-id="d207d-107">Remarks</span></span>  
 <span data-ttu-id="d207d-108">`GetFunction`如果帧不与任何特定的函数相关联，方法可能会失败。</span><span class="sxs-lookup"><span data-stu-id="d207d-108">The `GetFunction` method may fail if the frame is not associated with any particular function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d207d-109">要求</span><span class="sxs-lookup"><span data-stu-id="d207d-109">Requirements</span></span>  
 <span data-ttu-id="d207d-110">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="d207d-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d207d-111">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d207d-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d207d-112">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d207d-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d207d-113">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d207d-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
