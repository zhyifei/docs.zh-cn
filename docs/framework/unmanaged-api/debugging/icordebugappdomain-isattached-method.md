---
title: "ICorDebugAppDomain::IsAttached 方法"
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
- ICorDebugAppDomain.IsAttached
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAppDomain::IsAttached
helpviewer_keywords:
- IsAttached method [.NET Framework debugging]
- ICorDebugAppDomain::IsAttached method [.NET Framework debugging]
ms.assetid: af0c67c7-f53e-47c9-b84b-be50bd04903e
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: a1af550de7198041a885a788d6b36349c8e1c091
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugappdomainisattached-method"></a><span data-ttu-id="0b625-102">ICorDebugAppDomain::IsAttached 方法</span><span class="sxs-lookup"><span data-stu-id="0b625-102">ICorDebugAppDomain::IsAttached Method</span></span>
<span data-ttu-id="0b625-103">获取一个值，该值指示是否将调试器附加到应用程序域。</span><span class="sxs-lookup"><span data-stu-id="0b625-103">Gets a value that indicates whether the debugger is attached to the application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0b625-104">语法</span><span class="sxs-lookup"><span data-stu-id="0b625-104">Syntax</span></span>  
  
```  
HRESULT IsAttached (  
    [out] BOOL  *pbAttached  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="0b625-105">参数</span><span class="sxs-lookup"><span data-stu-id="0b625-105">Parameters</span></span>  
 `pbAttached`  
 <span data-ttu-id="0b625-106">[out]`true`如果调试器附加到应用程序域; 否则为`false`。</span><span class="sxs-lookup"><span data-stu-id="0b625-106">[out] `true` if the debugger is attached to the application domain; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0b625-107">备注</span><span class="sxs-lookup"><span data-stu-id="0b625-107">Remarks</span></span>  
 <span data-ttu-id="0b625-108">ICorDebugController 方法不能用，直到将调试器附加到应用程序域。</span><span class="sxs-lookup"><span data-stu-id="0b625-108">The ICorDebugController methods cannot be used until the debugger attaches to the application domain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0b625-109">惠?</span><span class="sxs-lookup"><span data-stu-id="0b625-109">Requirements</span></span>  
 <span data-ttu-id="0b625-110">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="0b625-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0b625-111">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0b625-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0b625-112">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0b625-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0b625-113">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0b625-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
