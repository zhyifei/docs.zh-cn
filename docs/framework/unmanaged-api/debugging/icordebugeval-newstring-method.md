---
title: "ICorDebugEval::NewString 方法"
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
- ICorDebugEval.NewString
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEval::NewString
helpviewer_keywords:
- NewString method [.NET Framework debugging]
- ICorDebugEval::NewString method [.NET Framework debugging]
ms.assetid: 29e7a14b-d50e-4852-bfda-011b76c0c9ee
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 6cc45d766801391fcd157c39357058be17759f8d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugevalnewstring-method"></a><span data-ttu-id="d36fe-102">ICorDebugEval::NewString 方法</span><span class="sxs-lookup"><span data-stu-id="d36fe-102">ICorDebugEval::NewString Method</span></span>
<span data-ttu-id="d36fe-103">分配具有指定内容的新字符串实例。</span><span class="sxs-lookup"><span data-stu-id="d36fe-103">Allocates a new string instance with the specified contents.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d36fe-104">语法</span><span class="sxs-lookup"><span data-stu-id="d36fe-104">Syntax</span></span>  
  
```  
HRESULT NewString (  
    [in] LPCWSTR   string  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d36fe-105">参数</span><span class="sxs-lookup"><span data-stu-id="d36fe-105">Parameters</span></span>  
 `string`  
 <span data-ttu-id="d36fe-106">[in]指向字符串的内容的指针。</span><span class="sxs-lookup"><span data-stu-id="d36fe-106">[in] Pointer to the contents for the string.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d36fe-107">备注</span><span class="sxs-lookup"><span data-stu-id="d36fe-107">Remarks</span></span>  
 <span data-ttu-id="d36fe-108">始终在线程当前执行的应用程序域中创建字符串。</span><span class="sxs-lookup"><span data-stu-id="d36fe-108">The string is always created in the application domain in which the thread is currently executing.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d36fe-109">惠?</span><span class="sxs-lookup"><span data-stu-id="d36fe-109">Requirements</span></span>  
 <span data-ttu-id="d36fe-110">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="d36fe-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d36fe-111">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d36fe-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d36fe-112">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d36fe-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d36fe-113">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d36fe-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
