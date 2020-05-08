---
title: ICorDebugAssembly2::IsFullyTrusted 方法
ms.date: 03/30/2017
api_name:
- ICorDebugAssembly2.IsFullyTrusted
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAssembly2::IsFullyTrusted
helpviewer_keywords:
- ICorDebugAssembly2::IsFullyTrusted method [.NET Framework debugging]
- IsFullyTrusted method [.NET Framework debugging]
ms.assetid: 26cbd27d-12bf-444a-8197-ccd14d37dda3
topic_type:
- apiref
ms.openlocfilehash: dd82709064fe7f7d912d93f4b3f0248769f02b9e
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2020
ms.locfileid: "82894890"
---
# <a name="icordebugassembly2isfullytrusted-method"></a><span data-ttu-id="a4da1-102">ICorDebugAssembly2::IsFullyTrusted 方法</span><span class="sxs-lookup"><span data-stu-id="a4da1-102">ICorDebugAssembly2::IsFullyTrusted Method</span></span>
<span data-ttu-id="a4da1-103">获取一个值，该值指示运行时安全系统是否已向程序集授予完全信任。</span><span class="sxs-lookup"><span data-stu-id="a4da1-103">Gets a value that indicates whether the assembly has been granted full trust by the runtime security system.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a4da1-104">语法</span><span class="sxs-lookup"><span data-stu-id="a4da1-104">Syntax</span></span>  
  
```cpp  
HRESULT IsFullyTrusted(  
    [out] BOOL *pbFullyTrusted  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a4da1-105">参数</span><span class="sxs-lookup"><span data-stu-id="a4da1-105">Parameters</span></span>  
 `pbFullyTrusted`  
 <span data-ttu-id="a4da1-106">弄`true`如果程序集已被运行时安全系统授予完全信任，则为; 否则为。否则为`false`。</span><span class="sxs-lookup"><span data-stu-id="a4da1-106">[out] `true` if the assembly has been granted full trust by the runtime security system; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a4da1-107">备注</span><span class="sxs-lookup"><span data-stu-id="a4da1-107">Remarks</span></span>  
 <span data-ttu-id="a4da1-108">如果程序集的安全策略尚未解析（即，如果尚未运行程序集中的代码），则此方法将返回 CORDBG_E_NOTREADY 的 HRESULT。</span><span class="sxs-lookup"><span data-stu-id="a4da1-108">This method returns an HRESULT of CORDBG_E_NOTREADY if the security policy for the assembly has not yet been resolved, that is, if no code in the assembly has been run yet.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a4da1-109">要求</span><span class="sxs-lookup"><span data-stu-id="a4da1-109">Requirements</span></span>  
 <span data-ttu-id="a4da1-110">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="a4da1-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a4da1-111">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a4da1-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a4da1-112">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a4da1-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a4da1-113">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a4da1-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
