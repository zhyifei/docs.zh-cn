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
ms.openlocfilehash: 87c43d6f05dffbf10ca1dd9253abfe893db9adf5
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73110484"
---
# <a name="icordebugappdomaingetid-method"></a><span data-ttu-id="5975b-102">ICorDebugAppDomain::GetId 方法</span><span class="sxs-lookup"><span data-stu-id="5975b-102">ICorDebugAppDomain::GetId Method</span></span>
<span data-ttu-id="5975b-103">获取应用程序域的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="5975b-103">Gets the unique identifier of the application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5975b-104">语法</span><span class="sxs-lookup"><span data-stu-id="5975b-104">Syntax</span></span>  
  
```cpp  
HRESULT GetID (  
    [out] ULONG32   *pId  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5975b-105">参数</span><span class="sxs-lookup"><span data-stu-id="5975b-105">Parameters</span></span>  
 `pId`  
 <span data-ttu-id="5975b-106">弄应用程序域的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="5975b-106">[out] The unique identifier of the application domain.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5975b-107">备注</span><span class="sxs-lookup"><span data-stu-id="5975b-107">Remarks</span></span>  
 <span data-ttu-id="5975b-108">应用程序域的标识符在包含进程中是唯一的。</span><span class="sxs-lookup"><span data-stu-id="5975b-108">The identifier for the application domain is unique within the containing process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5975b-109">要求</span><span class="sxs-lookup"><span data-stu-id="5975b-109">Requirements</span></span>  
 <span data-ttu-id="5975b-110">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="5975b-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5975b-111">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5975b-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5975b-112">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5975b-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5975b-113">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5975b-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
