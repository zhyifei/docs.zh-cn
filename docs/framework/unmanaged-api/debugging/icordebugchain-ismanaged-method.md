---
title: ICorDebugChain::IsManaged 方法
ms.date: 03/30/2017
api_name:
- ICorDebugChain.IsManaged
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugChain::IsManaged
helpviewer_keywords:
- ICorDebugChain::IsManaged method [.NET Framework debugging]
- IsManaged method, ICorDebugChain interface [.NET Framework debugging]
ms.assetid: 17b389a0-1a4d-4e8a-8613-9bc1769930f9
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a27ea95ca78f7db8f67ec2a13f02767e67619e97
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2019
ms.locfileid: "57488053"
---
# <a name="icordebugchainismanaged-method"></a><span data-ttu-id="3fb87-102">ICorDebugChain::IsManaged 方法</span><span class="sxs-lookup"><span data-stu-id="3fb87-102">ICorDebugChain::IsManaged Method</span></span>
<span data-ttu-id="3fb87-103">获取一个值，该值指示此链是否正在运行托管的代码。</span><span class="sxs-lookup"><span data-stu-id="3fb87-103">Gets a value that indicates whether this chain is running managed code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3fb87-104">语法</span><span class="sxs-lookup"><span data-stu-id="3fb87-104">Syntax</span></span>  
  
```  
HRESULT IsManaged (  
    [out] BOOL               *pManaged  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3fb87-105">参数</span><span class="sxs-lookup"><span data-stu-id="3fb87-105">Parameters</span></span>  
 `pManaged`  
 <span data-ttu-id="3fb87-106">[out]`true`如果此链正在运行托管的代码; 否则为`false`。</span><span class="sxs-lookup"><span data-stu-id="3fb87-106">[out] `true` if this chain is running managed code; otherwise, `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3fb87-107">要求</span><span class="sxs-lookup"><span data-stu-id="3fb87-107">Requirements</span></span>  
 <span data-ttu-id="3fb87-108">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="3fb87-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3fb87-109">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3fb87-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3fb87-110">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3fb87-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3fb87-111">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3fb87-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
