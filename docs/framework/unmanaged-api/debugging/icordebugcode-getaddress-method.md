---
title: ICorDebugCode::GetAddress 方法
ms.date: 03/30/2017
api_name:
- ICorDebugCode.GetAddress
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugCode::GetAddress
helpviewer_keywords:
- GetAddress method, ICorDebugCode interface [.NET Framework debugging]
- ICorDebugCode::GetAddress method [.NET Framework debugging]
ms.assetid: cc507cb0-df2e-49c2-b32e-0c3271a8df9a
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e2de22729fd3d7a511c1105ebf810d0402bd73a9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33402078"
---
# <a name="icordebugcodegetaddress-method"></a><span data-ttu-id="4e8af-102">ICorDebugCode::GetAddress 方法</span><span class="sxs-lookup"><span data-stu-id="4e8af-102">ICorDebugCode::GetAddress Method</span></span>
<span data-ttu-id="4e8af-103">此"icor 调试代码"接口表示的代码段中获取的相对虚拟地址 (RVA)。</span><span class="sxs-lookup"><span data-stu-id="4e8af-103">Gets the relative virtual address (RVA) of the code segment that this "ICorDebugCode" interface represents.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4e8af-104">语法</span><span class="sxs-lookup"><span data-stu-id="4e8af-104">Syntax</span></span>  
  
```  
HRESULT GetAddress (  
    [out] CORDB_ADDRESS *pStart  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="4e8af-105">参数</span><span class="sxs-lookup"><span data-stu-id="4e8af-105">Parameters</span></span>  
 `pStart`  
 <span data-ttu-id="4e8af-106">[out]代码段的 RVA 指向的指针。</span><span class="sxs-lookup"><span data-stu-id="4e8af-106">[out] A pointer to the RVA of the code segment.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4e8af-107">要求</span><span class="sxs-lookup"><span data-stu-id="4e8af-107">Requirements</span></span>  
 <span data-ttu-id="4e8af-108">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="4e8af-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4e8af-109">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4e8af-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4e8af-110">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4e8af-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4e8af-111">**.NET framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4e8af-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4e8af-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="4e8af-112">See Also</span></span>  
 
