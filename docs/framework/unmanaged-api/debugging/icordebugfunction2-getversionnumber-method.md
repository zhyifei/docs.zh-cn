---
title: "ICorDebugFunction2::GetVersionNumber 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICorDebugFunction2.GetVersionNumber
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFunction2::GetVersionNumber
helpviewer_keywords:
- ICorDebugFunction2::GetVersionNumber method [.NET Framework debugging]
- GetVersionNumber method, ICorDebugFunction2 interface [.NET Framework debugging]
ms.assetid: e3a1ce48-9bb9-4ed6-a5fe-5e1819a6333f
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 16902d1a50f691ae555fdbc964bb9a1c6bf563c4
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugfunction2getversionnumber-method"></a><span data-ttu-id="bbe3d-102">ICorDebugFunction2::GetVersionNumber 方法</span><span class="sxs-lookup"><span data-stu-id="bbe3d-102">ICorDebugFunction2::GetVersionNumber Method</span></span>
<span data-ttu-id="bbe3d-103">获取此函数的编辑并继续版本。</span><span class="sxs-lookup"><span data-stu-id="bbe3d-103">Gets the Edit and Continue version of this function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bbe3d-104">语法</span><span class="sxs-lookup"><span data-stu-id="bbe3d-104">Syntax</span></span>  
  
```  
HRESULT GetVersionNumber (  
    [out] ULONG32   *pnVersion  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="bbe3d-105">参数</span><span class="sxs-lookup"><span data-stu-id="bbe3d-105">Parameters</span></span>  
 `pnVersion`  
 <span data-ttu-id="bbe3d-106">[out]指向一个整数，表示此 ICorDebugFunction2 对象表示的函数的版本号的指针。</span><span class="sxs-lookup"><span data-stu-id="bbe3d-106">[out] A pointer to an integer that is the version number of the function that is represented by this ICorDebugFunction2 object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bbe3d-107">备注</span><span class="sxs-lookup"><span data-stu-id="bbe3d-107">Remarks</span></span>  
 <span data-ttu-id="bbe3d-108">运行时将跟踪的调试会话期间对每个模块所进行的编辑数。</span><span class="sxs-lookup"><span data-stu-id="bbe3d-108">The runtime keeps track of the number of edits that have taken place to each module during a debug session.</span></span> <span data-ttu-id="bbe3d-109">函数的版本号是以上引入了函数的编辑次数。</span><span class="sxs-lookup"><span data-stu-id="bbe3d-109">The version number of a function is one more than the number of the edit that introduced the function.</span></span> <span data-ttu-id="bbe3d-110">函数的原始版本是版本 1。</span><span class="sxs-lookup"><span data-stu-id="bbe3d-110">The function's original version is version 1.</span></span> <span data-ttu-id="bbe3d-111">该数字递增模块每次[icordebugmodule2:: Applychanges](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule2-applychanges-method.md)称为该模块。</span><span class="sxs-lookup"><span data-stu-id="bbe3d-111">The number is incremented for a module every time [ICorDebugModule2::ApplyChanges](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule2-applychanges-method.md) is called on that module.</span></span> <span data-ttu-id="bbe3d-112">因此，如果在第一个和第三个调用替换为函数的正文`ICorDebugModule2::ApplyChanges`，`GetVersionNumber`可能会返回版本 1、 2 或 4 该函数，但不是版本 3。</span><span class="sxs-lookup"><span data-stu-id="bbe3d-112">Thus, if a function’s body was replaced in the first and third call to `ICorDebugModule2::ApplyChanges`, `GetVersionNumber` may return version 1, 2, or 4 for that function, but not version 3.</span></span> <span data-ttu-id="bbe3d-113">（该函数将有没有版本 3。）</span><span class="sxs-lookup"><span data-stu-id="bbe3d-113">(That function would have no version 3.)</span></span>  
  
 <span data-ttu-id="bbe3d-114">为每个模块单独跟踪的版本号。</span><span class="sxs-lookup"><span data-stu-id="bbe3d-114">The version number is tracked separately for each module.</span></span> <span data-ttu-id="bbe3d-115">因此，如果上模块 1 和无模块 2 上执行四个编辑时，模块 1 你下一次编辑将的模块 1 中的所有编辑函数分配的版本号为 6。</span><span class="sxs-lookup"><span data-stu-id="bbe3d-115">So, if you perform four edits on Module 1, and none on Module 2, your next edit on Module 1 will assign a version number of 6 to all the edited functions in Module 1.</span></span> <span data-ttu-id="bbe3d-116">如果相同编辑改动模块 2，模块 2 中的函数将获得的版本号为 2。</span><span class="sxs-lookup"><span data-stu-id="bbe3d-116">If the same edit touches Module 2, the functions in Module 2 will get a version number of 2.</span></span>  
  
 <span data-ttu-id="bbe3d-117">通过获取的版本号`GetVersionNumber`方法可能会低于获取通过[icordebugfunction:: Getcurrentversionnumber](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction-getcurrentversionnumber-method.md)。</span><span class="sxs-lookup"><span data-stu-id="bbe3d-117">The version number obtained by the `GetVersionNumber` method may be lower than that obtained by [ICorDebugFunction::GetCurrentVersionNumber](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction-getcurrentversionnumber-method.md).</span></span>  
  
 <span data-ttu-id="bbe3d-118">[Icordebugcode:: Getversionnumber](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getversionnumber-method.md)方法执行相同的操作`ICorDebugFunction2::GetVersionNumber`。</span><span class="sxs-lookup"><span data-stu-id="bbe3d-118">The [ICorDebugCode::GetVersionNumber](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getversionnumber-method.md) method performs the same operation as `ICorDebugFunction2::GetVersionNumber`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bbe3d-119">惠?</span><span class="sxs-lookup"><span data-stu-id="bbe3d-119">Requirements</span></span>  
 <span data-ttu-id="bbe3d-120">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="bbe3d-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bbe3d-121">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="bbe3d-121">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="bbe3d-122">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bbe3d-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="bbe3d-123">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bbe3d-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
