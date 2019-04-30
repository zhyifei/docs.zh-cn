---
title: ICorDebugFunction2::GetJMCStatus 方法
ms.date: 03/30/2017
api_name:
- ICorDebugFunction2.GetJMCStatus
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFunction2::GetJMCStatus
helpviewer_keywords:
- ICorDebugFunction2::GetJMCStatus method [.NET Framework debugging]
- GetJMCStatus method [.NET Framework debugging]
ms.assetid: 840a71ed-bf5a-4f5e-8ed6-762222b34493
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d23a0a489cfe13201b7798920feb3528db3b0709
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61988658"
---
# <a name="icordebugfunction2getjmcstatus-method"></a><span data-ttu-id="58e07-102">ICorDebugFunction2::GetJMCStatus 方法</span><span class="sxs-lookup"><span data-stu-id="58e07-102">ICorDebugFunction2::GetJMCStatus Method</span></span>
<span data-ttu-id="58e07-103">获取一个值，该值指示是否由此 ICorDebugFunction2 对象的函数被标记为用户代码。</span><span class="sxs-lookup"><span data-stu-id="58e07-103">Gets a value that indicates whether the function that is represented by this ICorDebugFunction2 object is marked as user code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="58e07-104">语法</span><span class="sxs-lookup"><span data-stu-id="58e07-104">Syntax</span></span>  
  
```  
HRESULT GetJMCStatus (  
    [out] BOOL   *pbIsJustMyCode  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="58e07-105">参数</span><span class="sxs-lookup"><span data-stu-id="58e07-105">Parameters</span></span>  
 `pbIsJustMyCode`  
 <span data-ttu-id="58e07-106">[out]一个布尔值，是一个指向`true`，则此函数被标记为用户代码; 否则，值为`false`。</span><span class="sxs-lookup"><span data-stu-id="58e07-106">[out] A pointer to a Boolean value that is `true`, if this function is marked as user code; otherwise, the value is `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="58e07-107">备注</span><span class="sxs-lookup"><span data-stu-id="58e07-107">Remarks</span></span>  
 <span data-ttu-id="58e07-108">如果该函数表示由此`ICorDebugFunction2`不能调试`pbIsJustMyCode`始终会`false`。</span><span class="sxs-lookup"><span data-stu-id="58e07-108">If the function represented by this `ICorDebugFunction2` cannot be debugged, `pbIsJustMyCode` will always be `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="58e07-109">要求</span><span class="sxs-lookup"><span data-stu-id="58e07-109">Requirements</span></span>  
 <span data-ttu-id="58e07-110">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="58e07-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="58e07-111">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="58e07-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="58e07-112">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="58e07-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="58e07-113">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="58e07-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
