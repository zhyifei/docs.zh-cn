---
title: "ICorDebugAssembly2::IsFullyTrusted 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugAssembly2.IsFullyTrusted
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugAssembly2::IsFullyTrusted
helpviewer_keywords:
- ICorDebugAssembly2::IsFullyTrusted method [.NET Framework debugging]
- IsFullyTrusted method [.NET Framework debugging]
ms.assetid: 26cbd27d-12bf-444a-8197-ccd14d37dda3
topic_type: apiref
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 19058308876f80afdbaec73583242aa8ad3c33cb
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugassembly2isfullytrusted-method"></a><span data-ttu-id="4caaf-102">ICorDebugAssembly2::IsFullyTrusted 方法</span><span class="sxs-lookup"><span data-stu-id="4caaf-102">ICorDebugAssembly2::IsFullyTrusted Method</span></span>
<span data-ttu-id="4caaf-103">获取一个值，该值指示运行时安全系统是否已向程序集授予完全信任。</span><span class="sxs-lookup"><span data-stu-id="4caaf-103">Gets a value that indicates whether the assembly has been granted full trust by the runtime security system.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4caaf-104">语法</span><span class="sxs-lookup"><span data-stu-id="4caaf-104">Syntax</span></span>  
  
```  
HRESULT IsFullyTrusted(  
    [out] BOOL *pbFullyTrusted  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="4caaf-105">参数</span><span class="sxs-lookup"><span data-stu-id="4caaf-105">Parameters</span></span>  
 `pbFullyTrusted`  
 <span data-ttu-id="4caaf-106">[out]`true`程序集是否已被授予完全信任，由运行时安全系统中; 否则为`false`。</span><span class="sxs-lookup"><span data-stu-id="4caaf-106">[out] `true` if the assembly has been granted full trust by the runtime security system; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4caaf-107">备注</span><span class="sxs-lookup"><span data-stu-id="4caaf-107">Remarks</span></span>  
 <span data-ttu-id="4caaf-108">此方法返回 HRESULT 的 CORDBG_E_NOTREADY 如果程序集的安全策略尚未解决，即，如果程序集中的任何代码均已尚未运行。</span><span class="sxs-lookup"><span data-stu-id="4caaf-108">This method returns an HRESULT of CORDBG_E_NOTREADY if the security policy for the assembly has not yet been resolved, that is, if no code in the assembly has been run yet.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4caaf-109">要求</span><span class="sxs-lookup"><span data-stu-id="4caaf-109">Requirements</span></span>  
 <span data-ttu-id="4caaf-110">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="4caaf-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4caaf-111">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4caaf-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4caaf-112">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4caaf-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4caaf-113">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4caaf-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
