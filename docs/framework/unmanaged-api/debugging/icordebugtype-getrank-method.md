---
title: ICorDebugType::GetRank 方法
ms.date: 03/30/2017
api_name:
- ICorDebugType.GetRank
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugType::GetRank
helpviewer_keywords:
- GetRank method, ICorDebugType interface [.NET Framework debugging]
- ICorDebugType::GetRank method [.NET Framework debugging]
ms.assetid: 72d3d927-f590-4f2d-8f60-448f3dfb96af
topic_type:
- apiref
ms.openlocfilehash: 9a00177faabfcad56d70ec5c64328c90675c1532
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73138763"
---
# <a name="icordebugtypegetrank-method"></a><span data-ttu-id="44a1d-102">ICorDebugType::GetRank 方法</span><span class="sxs-lookup"><span data-stu-id="44a1d-102">ICorDebugType::GetRank Method</span></span>
<span data-ttu-id="44a1d-103">获取数组类型中的维度数。</span><span class="sxs-lookup"><span data-stu-id="44a1d-103">Gets the number of dimensions in an array type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="44a1d-104">语法</span><span class="sxs-lookup"><span data-stu-id="44a1d-104">Syntax</span></span>  
  
```cpp  
HRESULT GetRank (  
    [out] ULONG32   *pnRank  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="44a1d-105">参数</span><span class="sxs-lookup"><span data-stu-id="44a1d-105">Parameters</span></span>  
 `pnRank`  
 <span data-ttu-id="44a1d-106">弄指向维度数的指针。</span><span class="sxs-lookup"><span data-stu-id="44a1d-106">[out] A pointer to the number of dimensions.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="44a1d-107">要求</span><span class="sxs-lookup"><span data-stu-id="44a1d-107">Requirements</span></span>  
 <span data-ttu-id="44a1d-108">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="44a1d-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="44a1d-109">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="44a1d-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="44a1d-110">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="44a1d-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="44a1d-111">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="44a1d-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
