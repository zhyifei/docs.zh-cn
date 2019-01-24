---
title: ICorDebugCode::GetEnCRemapSequencePoints 方法
ms.date: 03/30/2017
api_name:
- ICorDebugCode.GetEnCRemapSequencePoints
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugCode::GetEnCRemapSequencePoints
helpviewer_keywords:
- GetEnCRemapSequencePoints method [.NET Framework debugging]
- ICorDebugCode::GetEnCRemapSequencePoints method [.NET Framework debugging]
ms.assetid: 8463a98a-de4a-418e-beb0-9611885ae6b0
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: bea6b11437367d5ba14167d9800f6c43e117d548
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54533320"
---
# <a name="icordebugcodegetencremapsequencepoints-method"></a><span data-ttu-id="af16f-102">ICorDebugCode::GetEnCRemapSequencePoints 方法</span><span class="sxs-lookup"><span data-stu-id="af16f-102">ICorDebugCode::GetEnCRemapSequencePoints Method</span></span>
<span data-ttu-id="af16f-103">当前版本的.NET Framework 中未实现此方法。</span><span class="sxs-lookup"><span data-stu-id="af16f-103">This method is not implemented in the current version of the .NET Framework.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="af16f-104">语法</span><span class="sxs-lookup"><span data-stu-id="af16f-104">Syntax</span></span>  
  
```  
HRESULT GetEnCRemapSequencePoints(  
    [in] ULONG32 cMap,  
    [out] ULONG32 *pcMap,  
    [out, size_is(cMap), length_is(*pcMap)]  
        ULONG32 offsets[]  
);  
```  
  
## <a name="see-also"></a><span data-ttu-id="af16f-105">请参阅</span><span class="sxs-lookup"><span data-stu-id="af16f-105">See also</span></span>

