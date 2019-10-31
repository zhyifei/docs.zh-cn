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
ms.openlocfilehash: df73663f714b0c1c3d3ae5dfb53e8e84196a8f37
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73125679"
---
# <a name="icordebugcodegetaddress-method"></a><span data-ttu-id="0bf92-102">ICorDebugCode::GetAddress 方法</span><span class="sxs-lookup"><span data-stu-id="0bf92-102">ICorDebugCode::GetAddress Method</span></span>
<span data-ttu-id="0bf92-103">获取此 "ICorDebugCode" 接口表示的代码段的相对虚拟地址（RVA）。</span><span class="sxs-lookup"><span data-stu-id="0bf92-103">Gets the relative virtual address (RVA) of the code segment that this "ICorDebugCode" interface represents.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0bf92-104">语法</span><span class="sxs-lookup"><span data-stu-id="0bf92-104">Syntax</span></span>  
  
```cpp  
HRESULT GetAddress (  
    [out] CORDB_ADDRESS *pStart  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0bf92-105">参数</span><span class="sxs-lookup"><span data-stu-id="0bf92-105">Parameters</span></span>  
 `pStart`  
 <span data-ttu-id="0bf92-106">弄指向代码段的 RVA 的指针。</span><span class="sxs-lookup"><span data-stu-id="0bf92-106">[out] A pointer to the RVA of the code segment.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0bf92-107">要求</span><span class="sxs-lookup"><span data-stu-id="0bf92-107">Requirements</span></span>  
 <span data-ttu-id="0bf92-108">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="0bf92-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0bf92-109">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0bf92-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0bf92-110">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0bf92-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0bf92-111">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0bf92-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
