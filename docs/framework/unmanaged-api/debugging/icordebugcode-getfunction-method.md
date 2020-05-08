---
title: ICorDebugCode::GetFunction 方法
ms.date: 03/30/2017
api_name:
- ICorDebugCode.GetFunction
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugCode::GetFunction
helpviewer_keywords:
- GetFunction method, ICorDebugCode interface [.NET Framework debugging]
- ICorDebugCode::GetFunction method [.NET Framework debugging]
ms.assetid: c568b737-fdb2-4816-accd-051f5ab760f1
topic_type:
- apiref
ms.openlocfilehash: 9f785eafa8925324e3bd269ca08a3b1367b74c44
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2020
ms.locfileid: "82893589"
---
# <a name="icordebugcodegetfunction-method"></a><span data-ttu-id="eb15e-102">ICorDebugCode::GetFunction 方法</span><span class="sxs-lookup"><span data-stu-id="eb15e-102">ICorDebugCode::GetFunction Method</span></span>
<span data-ttu-id="eb15e-103">获取与此 "ICorDebugCode" 关联的 "ICorDebugFunction"。</span><span class="sxs-lookup"><span data-stu-id="eb15e-103">Gets the "ICorDebugFunction" associated with this "ICorDebugCode".</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eb15e-104">语法</span><span class="sxs-lookup"><span data-stu-id="eb15e-104">Syntax</span></span>  
  
```cpp  
HRESULT GetFunction (  
    [out] ICorDebugFunction **ppFunction  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="eb15e-105">参数</span><span class="sxs-lookup"><span data-stu-id="eb15e-105">Parameters</span></span>  
 `ppFunction`  
 <span data-ttu-id="eb15e-106">弄指向函数的地址的指针。</span><span class="sxs-lookup"><span data-stu-id="eb15e-106">[out] A pointer to the address of the function.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="eb15e-107">备注</span><span class="sxs-lookup"><span data-stu-id="eb15e-107">Remarks</span></span>  
 <span data-ttu-id="eb15e-108">`ICorDebugCode`和`ICorDebugFunction`保持一对一关系。</span><span class="sxs-lookup"><span data-stu-id="eb15e-108">`ICorDebugCode` and `ICorDebugFunction` maintain a one-to-one relationship.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="eb15e-109">要求</span><span class="sxs-lookup"><span data-stu-id="eb15e-109">Requirements</span></span>  
 <span data-ttu-id="eb15e-110">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="eb15e-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="eb15e-111">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="eb15e-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="eb15e-112">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="eb15e-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="eb15e-113">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="eb15e-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
