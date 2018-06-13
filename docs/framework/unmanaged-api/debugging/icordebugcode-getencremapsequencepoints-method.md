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
ms.openlocfilehash: fd0607f2523e6f05065acc0078f4cb2848afd928
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33403739"
---
# <a name="icordebugcodegetencremapsequencepoints-method"></a><span data-ttu-id="ef08d-102">ICorDebugCode::GetEnCRemapSequencePoints 方法</span><span class="sxs-lookup"><span data-stu-id="ef08d-102">ICorDebugCode::GetEnCRemapSequencePoints Method</span></span>
<span data-ttu-id="ef08d-103">.NET Framework 的当前版本中未实现此方法。</span><span class="sxs-lookup"><span data-stu-id="ef08d-103">This method is not implemented in the current version of the .NET Framework.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ef08d-104">语法</span><span class="sxs-lookup"><span data-stu-id="ef08d-104">Syntax</span></span>  
  
```  
HRESULT GetEnCRemapSequencePoints(  
    [in] ULONG32 cMap,  
    [out] ULONG32 *pcMap,  
    [out, size_is(cMap), length_is(*pcMap)]  
        ULONG32 offsets[]  
);  
```  
  
## <a name="see-also"></a><span data-ttu-id="ef08d-105">请参阅</span><span class="sxs-lookup"><span data-stu-id="ef08d-105">See Also</span></span>  
 
