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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 8122f1b5017faac3425d59d12d77f84180134d65
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33401624"
---
# <a name="icordebugappdomaingetid-method"></a><span data-ttu-id="6eef1-102">ICorDebugAppDomain::GetId 方法</span><span class="sxs-lookup"><span data-stu-id="6eef1-102">ICorDebugAppDomain::GetId Method</span></span>
<span data-ttu-id="6eef1-103">获取应用程序域的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="6eef1-103">Gets the unique identifier of the application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6eef1-104">语法</span><span class="sxs-lookup"><span data-stu-id="6eef1-104">Syntax</span></span>  
  
```  
HRESULT GetID (  
    [out] ULONG32   *pId  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="6eef1-105">参数</span><span class="sxs-lookup"><span data-stu-id="6eef1-105">Parameters</span></span>  
 `pId`  
 <span data-ttu-id="6eef1-106">[out]应用程序域的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="6eef1-106">[out] The unique identifier of the application domain.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6eef1-107">备注</span><span class="sxs-lookup"><span data-stu-id="6eef1-107">Remarks</span></span>  
 <span data-ttu-id="6eef1-108">应用程序域的标识符是包含进程内唯一的。</span><span class="sxs-lookup"><span data-stu-id="6eef1-108">The identifier for the application domain is unique within the containing process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6eef1-109">要求</span><span class="sxs-lookup"><span data-stu-id="6eef1-109">Requirements</span></span>  
 <span data-ttu-id="6eef1-110">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="6eef1-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6eef1-111">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6eef1-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6eef1-112">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6eef1-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6eef1-113">**.NET framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6eef1-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
