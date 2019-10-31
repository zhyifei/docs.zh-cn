---
title: ICorDebugAppDomain::IsAttached 方法
ms.date: 03/30/2017
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
ms.openlocfilehash: 30e0b0c4ed9bac4abd1dc185031e41c1e3ed014a
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73134671"
---
# <a name="icordebugappdomainisattached-method"></a><span data-ttu-id="2d2d2-102">ICorDebugAppDomain::IsAttached 方法</span><span class="sxs-lookup"><span data-stu-id="2d2d2-102">ICorDebugAppDomain::IsAttached Method</span></span>
<span data-ttu-id="2d2d2-103">获取一个值，该值指示调试器是否已附加到应用程序域。</span><span class="sxs-lookup"><span data-stu-id="2d2d2-103">Gets a value that indicates whether the debugger is attached to the application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2d2d2-104">语法</span><span class="sxs-lookup"><span data-stu-id="2d2d2-104">Syntax</span></span>  
  
```cpp  
HRESULT IsAttached (  
    [out] BOOL  *pbAttached  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2d2d2-105">参数</span><span class="sxs-lookup"><span data-stu-id="2d2d2-105">Parameters</span></span>  
 `pbAttached`  
 <span data-ttu-id="2d2d2-106">[out] 如果调试器附加到应用程序域，则 `true`;否则，`false`。</span><span class="sxs-lookup"><span data-stu-id="2d2d2-106">[out] `true` if the debugger is attached to the application domain; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2d2d2-107">备注</span><span class="sxs-lookup"><span data-stu-id="2d2d2-107">Remarks</span></span>  
 <span data-ttu-id="2d2d2-108">在调试器附加到应用程序域之前，不能使用 ICorDebugController 方法。</span><span class="sxs-lookup"><span data-stu-id="2d2d2-108">The ICorDebugController methods cannot be used until the debugger attaches to the application domain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2d2d2-109">要求</span><span class="sxs-lookup"><span data-stu-id="2d2d2-109">Requirements</span></span>  
 <span data-ttu-id="2d2d2-110">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="2d2d2-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2d2d2-111">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2d2d2-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2d2d2-112">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2d2d2-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2d2d2-113">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2d2d2-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
