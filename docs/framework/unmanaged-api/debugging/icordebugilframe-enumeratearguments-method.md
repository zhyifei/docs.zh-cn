---
title: "ICorDebugILFrame::EnumerateArguments 方法"
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
- ICorDebugILFrame.EnumerateArguments
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugILFrame::EnumerateArguments
helpviewer_keywords:
- ICorDebugILFrame::EnumerateArguments method [.NET Framework debugging]
- EnumerateArguments method [.NET Framework debugging]
ms.assetid: 00ac81e2-a774-422a-bd88-54a4b3c99f73
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 474118abc505928d16737d792a619e75f1209344
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugilframeenumeratearguments-method"></a><span data-ttu-id="20ae7-102">ICorDebugILFrame::EnumerateArguments 方法</span><span class="sxs-lookup"><span data-stu-id="20ae7-102">ICorDebugILFrame::EnumerateArguments Method</span></span>
<span data-ttu-id="20ae7-103">此帧中获取自变量的枚举数。</span><span class="sxs-lookup"><span data-stu-id="20ae7-103">Gets an enumerator for the arguments in this frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="20ae7-104">语法</span><span class="sxs-lookup"><span data-stu-id="20ae7-104">Syntax</span></span>  
  
```  
HRESULT EnumerateArguments (  
    [out] ICorDebugValueEnum    **ppValueEnum  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="20ae7-105">参数</span><span class="sxs-lookup"><span data-stu-id="20ae7-105">Parameters</span></span>  
 `ppValueEnum`  
 <span data-ttu-id="20ae7-106">[out]指向的地址是此帧中的自变量的枚举器的 ICorDebugValueEnum 对象的指针。</span><span class="sxs-lookup"><span data-stu-id="20ae7-106">[out] A pointer to the address of an ICorDebugValueEnum object that is the enumerator for the arguments in this frame.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="20ae7-107">备注</span><span class="sxs-lookup"><span data-stu-id="20ae7-107">Remarks</span></span>  
 <span data-ttu-id="20ae7-108">`EnumerateArguments`获取枚举数，可以列出此 ICorDebugILFrame 对象表示的调用帧中可用的自变量。</span><span class="sxs-lookup"><span data-stu-id="20ae7-108">`EnumerateArguments` gets an enumerator that can list the arguments available in the call frame that is represented by this ICorDebugILFrame object.</span></span> <span data-ttu-id="20ae7-109">列表中会包含由自变量[vararg](/cpp/windows/vararg) （即，数目可变的参数） 不是自变量以及`vararg`。</span><span class="sxs-lookup"><span data-stu-id="20ae7-109">The list will include arguments that are [vararg](/cpp/windows/vararg) (that is, a variable number of arguments) as well as arguments that are not `vararg`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="20ae7-110">惠?</span><span class="sxs-lookup"><span data-stu-id="20ae7-110">Requirements</span></span>  
 <span data-ttu-id="20ae7-111">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="20ae7-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="20ae7-112">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="20ae7-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="20ae7-113">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="20ae7-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="20ae7-114">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="20ae7-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
