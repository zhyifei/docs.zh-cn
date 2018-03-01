---
title: "ICorDebugILFrame::EnumerateLocalVariables 方法"
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
- ICorDebugILFrame.EnumerateLocalVariables
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugILFrame::EnumerateLocalVariables
helpviewer_keywords:
- EnumerateLocalVariables method [.NET Framework debugging]
- ICorDebugILFrame::EnumerateLocalVariables method [.NET Framework debugging]
ms.assetid: 1a67fa1b-2419-4cd0-aad4-6f46a0719b4b
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 3a1b53dbefefcea6003ec4a61c8169ed96bac701
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugilframeenumeratelocalvariables-method"></a><span data-ttu-id="8f633-102">ICorDebugILFrame::EnumerateLocalVariables 方法</span><span class="sxs-lookup"><span data-stu-id="8f633-102">ICorDebugILFrame::EnumerateLocalVariables Method</span></span>
<span data-ttu-id="8f633-103">此帧中获取的本地变量的枚举数。</span><span class="sxs-lookup"><span data-stu-id="8f633-103">Gets an enumerator for the local variables in this frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8f633-104">语法</span><span class="sxs-lookup"><span data-stu-id="8f633-104">Syntax</span></span>  
  
```  
HRESULT EnumerateLocalVariables(   
    [out] ICorDebugValueEnum    **ppValueEnum  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="8f633-105">参数</span><span class="sxs-lookup"><span data-stu-id="8f633-105">Parameters</span></span>  
 `ppValueEnum`  
 <span data-ttu-id="8f633-106">[out]指向的地址是此帧中局部变量的枚举器的 ICorDebugValueEnum 对象的指针。</span><span class="sxs-lookup"><span data-stu-id="8f633-106">[out] A pointer to the address of an ICorDebugValueEnum object that is the enumerator for the local variables in this frame.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8f633-107">备注</span><span class="sxs-lookup"><span data-stu-id="8f633-107">Remarks</span></span>  
 <span data-ttu-id="8f633-108">`EnumerateLocalVariables`获取可以列出此 ICorDebugILFrame 对象表示的调用帧中可用的本地变量的枚举器。</span><span class="sxs-lookup"><span data-stu-id="8f633-108">`EnumerateLocalVariables` gets an enumerator that can list the local variables available in the call frame that is represented by this ICorDebugILFrame object.</span></span> <span data-ttu-id="8f633-109">列表可能不包括所有的局部变量中正在运行的函数，因为其中一些可能未处于活动状态。</span><span class="sxs-lookup"><span data-stu-id="8f633-109">The list may not include all of the local variables in the running function, because some of them may not be active.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8f633-110">惠?</span><span class="sxs-lookup"><span data-stu-id="8f633-110">Requirements</span></span>  
 <span data-ttu-id="8f633-111">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="8f633-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8f633-112">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8f633-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8f633-113">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8f633-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8f633-114">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8f633-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
