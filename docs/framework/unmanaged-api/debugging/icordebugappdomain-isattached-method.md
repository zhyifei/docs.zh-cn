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
ms.openlocfilehash: a2f6df7647ffe9f2adff963b6629ed29ece053c0
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2020
ms.locfileid: "82895164"
---
# <a name="icordebugappdomainisattached-method"></a><span data-ttu-id="442fa-102">ICorDebugAppDomain::IsAttached 方法</span><span class="sxs-lookup"><span data-stu-id="442fa-102">ICorDebugAppDomain::IsAttached Method</span></span>
<span data-ttu-id="442fa-103">获取一个值，该值指示调试器是否已附加到应用程序域。</span><span class="sxs-lookup"><span data-stu-id="442fa-103">Gets a value that indicates whether the debugger is attached to the application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="442fa-104">语法</span><span class="sxs-lookup"><span data-stu-id="442fa-104">Syntax</span></span>  
  
```cpp  
HRESULT IsAttached (  
    [out] BOOL  *pbAttached  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="442fa-105">参数</span><span class="sxs-lookup"><span data-stu-id="442fa-105">Parameters</span></span>  
 `pbAttached`  
 <span data-ttu-id="442fa-106">弄`true`如果调试器附加到应用程序域，则为; 否则为。否则为`false`。</span><span class="sxs-lookup"><span data-stu-id="442fa-106">[out] `true` if the debugger is attached to the application domain; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="442fa-107">备注</span><span class="sxs-lookup"><span data-stu-id="442fa-107">Remarks</span></span>  
 <span data-ttu-id="442fa-108">在调试器附加到应用程序域之前，不能使用 ICorDebugController 方法。</span><span class="sxs-lookup"><span data-stu-id="442fa-108">The ICorDebugController methods cannot be used until the debugger attaches to the application domain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="442fa-109">要求</span><span class="sxs-lookup"><span data-stu-id="442fa-109">Requirements</span></span>  
 <span data-ttu-id="442fa-110">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="442fa-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="442fa-111">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="442fa-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="442fa-112">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="442fa-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="442fa-113">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="442fa-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
