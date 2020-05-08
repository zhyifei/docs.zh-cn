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
ms.openlocfilehash: 55036fcdbd186f91c0e94fb05f3023cf614751f7
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2020
ms.locfileid: "82894255"
---
# <a name="icordebugchainismanaged-method"></a><span data-ttu-id="ba994-102">ICorDebugChain::IsManaged 方法</span><span class="sxs-lookup"><span data-stu-id="ba994-102">ICorDebugChain::IsManaged Method</span></span>
<span data-ttu-id="ba994-103">获取一个值，该值指示此链是否正在运行托管代码。</span><span class="sxs-lookup"><span data-stu-id="ba994-103">Gets a value that indicates whether this chain is running managed code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ba994-104">语法</span><span class="sxs-lookup"><span data-stu-id="ba994-104">Syntax</span></span>  
  
```cpp  
HRESULT IsManaged (  
    [out] BOOL               *pManaged  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ba994-105">参数</span><span class="sxs-lookup"><span data-stu-id="ba994-105">Parameters</span></span>  
 `pManaged`  
 <span data-ttu-id="ba994-106">弄`true`如果此链正在运行托管代码，则为;否则为`false`。</span><span class="sxs-lookup"><span data-stu-id="ba994-106">[out] `true` if this chain is running managed code; otherwise, `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ba994-107">要求</span><span class="sxs-lookup"><span data-stu-id="ba994-107">Requirements</span></span>  
 <span data-ttu-id="ba994-108">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="ba994-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ba994-109">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ba994-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ba994-110">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ba994-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ba994-111">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ba994-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
