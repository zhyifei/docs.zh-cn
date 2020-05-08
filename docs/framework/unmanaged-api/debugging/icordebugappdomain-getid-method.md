---
title: ICorDebugAppDomain::GetId 方法
ms.date: 03/30/2017
api_name:
- ICorDebugAppDomain.GetId
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAppDomain::GetId
helpviewer_keywords:
- GetId method, ICorDebugAppDomain interface [.NET Framework debugging]
- ICorDebugAppDomain::GetId method [.NET Framework debugging]
ms.assetid: 32c27576-71fa-42ee-8230-67b92913ea08
topic_type:
- apiref
ms.openlocfilehash: 63346c679efc083dea9ab0eaa4f983a5308695f8
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2020
ms.locfileid: "82895256"
---
# <a name="icordebugappdomaingetid-method"></a><span data-ttu-id="e4d5a-102">ICorDebugAppDomain::GetId 方法</span><span class="sxs-lookup"><span data-stu-id="e4d5a-102">ICorDebugAppDomain::GetId Method</span></span>
<span data-ttu-id="e4d5a-103">获取应用程序域的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="e4d5a-103">Gets the unique identifier of the application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e4d5a-104">语法</span><span class="sxs-lookup"><span data-stu-id="e4d5a-104">Syntax</span></span>  
  
```cpp  
HRESULT GetID (  
    [out] ULONG32   *pId  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e4d5a-105">参数</span><span class="sxs-lookup"><span data-stu-id="e4d5a-105">Parameters</span></span>  
 `pId`  
 <span data-ttu-id="e4d5a-106">弄应用程序域的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="e4d5a-106">[out] The unique identifier of the application domain.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e4d5a-107">备注</span><span class="sxs-lookup"><span data-stu-id="e4d5a-107">Remarks</span></span>  
 <span data-ttu-id="e4d5a-108">应用程序域的标识符在包含进程中是唯一的。</span><span class="sxs-lookup"><span data-stu-id="e4d5a-108">The identifier for the application domain is unique within the containing process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e4d5a-109">要求</span><span class="sxs-lookup"><span data-stu-id="e4d5a-109">Requirements</span></span>  
 <span data-ttu-id="e4d5a-110">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="e4d5a-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e4d5a-111">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e4d5a-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e4d5a-112">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e4d5a-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e4d5a-113">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e4d5a-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
