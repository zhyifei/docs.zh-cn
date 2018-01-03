---
title: "ICorDebugAppDomain::EnumerateBreakpoints 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugAppDomain.EnumerateBreakpoints
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugAppDomain::EnumerateBreakpoints
helpviewer_keywords:
- ICorDebugAppDomain::EnumerateBreakpoints method [.NET Framework debugging]
- EnumerateBreakpoints method [.NET Framework debugging]
ms.assetid: 206069c5-25cb-4794-9d69-67c5aa7ed0af
topic_type: apiref
caps.latest.revision: "14"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 2363b3159bef4453eb3eeb910d3d304806c56e6e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugappdomainenumeratebreakpoints-method"></a><span data-ttu-id="24648-102">ICorDebugAppDomain::EnumerateBreakpoints 方法</span><span class="sxs-lookup"><span data-stu-id="24648-102">ICorDebugAppDomain::EnumerateBreakpoints Method</span></span>
<span data-ttu-id="24648-103">应用程序域中获取所有活动断点的枚举数。</span><span class="sxs-lookup"><span data-stu-id="24648-103">Gets an enumerator for all active breakpoints in the application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="24648-104">语法</span><span class="sxs-lookup"><span data-stu-id="24648-104">Syntax</span></span>  
  
```  
HRESULT EnumerateBreakpoints (  
    [out] ICorDebugBreakpointEnum   **ppBreakpoints  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="24648-105">参数</span><span class="sxs-lookup"><span data-stu-id="24648-105">Parameters</span></span>  
 `ppBreakpoints`  
 <span data-ttu-id="24648-106">[out]指向的地址是应用程序域中的所有活动断点的枚举器的 ICorDebugBreakpointEnum 对象的指针。</span><span class="sxs-lookup"><span data-stu-id="24648-106">[out] A pointer to the address of an ICorDebugBreakpointEnum object that is the enumerator for all active breakpoints in the application domain.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="24648-107">备注</span><span class="sxs-lookup"><span data-stu-id="24648-107">Remarks</span></span>  
 <span data-ttu-id="24648-108">枚举器包括所有类型的断点，包括函数断点和数据断点。</span><span class="sxs-lookup"><span data-stu-id="24648-108">The enumerator includes all types of breakpoints, including function breakpoints and data breakpoints.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="24648-109">惠?</span><span class="sxs-lookup"><span data-stu-id="24648-109">Requirements</span></span>  
 <span data-ttu-id="24648-110">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="24648-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="24648-111">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="24648-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="24648-112">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="24648-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="24648-113">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="24648-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
