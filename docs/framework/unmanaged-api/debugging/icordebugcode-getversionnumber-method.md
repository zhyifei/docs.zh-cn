---
title: "ICorDebugCode::GetVersionNumber 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugCode.GetVersionNumber
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugCode::GetVersionNumber
helpviewer_keywords:
- GetVersionNumber method, ICorDebugCode interface [.NET Framework debugging]
- ICorDebugCode::GetVersionNumber method [.NET Framework debugging]
ms.assetid: c8e02518-679f-4e9f-8a28-ba4a89a3876f
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: cd467f047131bbb078c72db9daca2cbc5a87a7be
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugcodegetversionnumber-method"></a><span data-ttu-id="64995-102">ICorDebugCode::GetVersionNumber 方法</span><span class="sxs-lookup"><span data-stu-id="64995-102">ICorDebugCode::GetVersionNumber Method</span></span>
<span data-ttu-id="64995-103">获取标识此"icor 调试代码"表示的代码的版本的基于 1 的数字。</span><span class="sxs-lookup"><span data-stu-id="64995-103">Gets the one-based number that identifies the version of the code that this "ICorDebugCode" represents.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="64995-104">语法</span><span class="sxs-lookup"><span data-stu-id="64995-104">Syntax</span></span>  
  
```  
HRESULT GetVersionNumber (  
    [out] ULONG32    *nVersion  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="64995-105">参数</span><span class="sxs-lookup"><span data-stu-id="64995-105">Parameters</span></span>  
 `nVersion`  
 <span data-ttu-id="64995-106">[out]指向代码的版本号的指针。</span><span class="sxs-lookup"><span data-stu-id="64995-106">[out] A pointer to the version number of the code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="64995-107">备注</span><span class="sxs-lookup"><span data-stu-id="64995-107">Remarks</span></span>  
 <span data-ttu-id="64995-108">编辑并继续 (EnC) 操作执行的代码，每次都会递增的版本号。</span><span class="sxs-lookup"><span data-stu-id="64995-108">The version number is incremented each time an edit-and-continue (EnC) operation is performed on the code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="64995-109">要求</span><span class="sxs-lookup"><span data-stu-id="64995-109">Requirements</span></span>  
 <span data-ttu-id="64995-110">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="64995-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="64995-111">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="64995-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="64995-112">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="64995-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="64995-113">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="64995-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="64995-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="64995-114">See Also</span></span>  
 
