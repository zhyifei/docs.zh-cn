---
title: ICorDebugEnum::GetCount 方法
ms.date: 03/30/2017
api_name:
- ICorDebugEnum.GetCount
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEnum::GetCount
helpviewer_keywords:
- ICorDebugEnum::GetCount method [.NET Framework debugging]
- GetCount method, ICorDebugEnum interface [.NET Framework debugging]
ms.assetid: d8a74304-1cb2-4977-a21d-e1af48c563ff
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5eddad89c60f25c957a06822d54cc73501b974ee
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33415624"
---
# <a name="icordebugenumgetcount-method"></a><span data-ttu-id="e7ed1-102">ICorDebugEnum::GetCount 方法</span><span class="sxs-lookup"><span data-stu-id="e7ed1-102">ICorDebugEnum::GetCount Method</span></span>
<span data-ttu-id="e7ed1-103">枚举中获取项的数目。</span><span class="sxs-lookup"><span data-stu-id="e7ed1-103">Gets the number of items in the enumeration.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e7ed1-104">语法</span><span class="sxs-lookup"><span data-stu-id="e7ed1-104">Syntax</span></span>  
  
```  
HRESULT GetCount (  
    [out] ULONG *pcelt  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e7ed1-105">参数</span><span class="sxs-lookup"><span data-stu-id="e7ed1-105">Parameters</span></span>  
 `pcelt`  
 <span data-ttu-id="e7ed1-106">[out]一个指向枚举中的项的数目。</span><span class="sxs-lookup"><span data-stu-id="e7ed1-106">[out] A pointer to the number of items in the enumeration.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e7ed1-107">要求</span><span class="sxs-lookup"><span data-stu-id="e7ed1-107">Requirements</span></span>  
 <span data-ttu-id="e7ed1-108">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="e7ed1-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e7ed1-109">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e7ed1-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e7ed1-110">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e7ed1-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e7ed1-111">**.NET framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e7ed1-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
