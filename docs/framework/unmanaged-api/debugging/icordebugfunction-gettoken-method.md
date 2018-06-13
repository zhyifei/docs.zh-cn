---
title: ICorDebugFunction::GetToken 方法
ms.date: 03/30/2017
api_name:
- ICorDebugFunction.GetToken
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFunction::GetToken
helpviewer_keywords:
- ICorDebugFunction::GetToken method [.NET Framework debugging]
- GetToken method, ICorDebugFunction interface [.NET Framework debugging]
ms.assetid: c6bbf479-062e-48e9-9c70-0f92e293e36a
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: acfb8910df6e20bf55ed33fdbb9b1c30d22f4684
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33412047"
---
# <a name="icordebugfunctiongettoken-method"></a><span data-ttu-id="004e4-102">ICorDebugFunction::GetToken 方法</span><span class="sxs-lookup"><span data-stu-id="004e4-102">ICorDebugFunction::GetToken Method</span></span>
<span data-ttu-id="004e4-103">获取此函数的元数据令牌。</span><span class="sxs-lookup"><span data-stu-id="004e4-103">Gets the metadata token for this function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="004e4-104">语法</span><span class="sxs-lookup"><span data-stu-id="004e4-104">Syntax</span></span>  
  
```  
HRESULT GetToken (  
    [out] mdMethodDef *pMethodDef  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="004e4-105">参数</span><span class="sxs-lookup"><span data-stu-id="004e4-105">Parameters</span></span>  
 `pMethodDef`  
 <span data-ttu-id="004e4-106">[out]指向的指针`mdMethodDef`引用此函数的元数据的令牌。</span><span class="sxs-lookup"><span data-stu-id="004e4-106">[out] A pointer to an `mdMethodDef` token that references the metadata for this function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="004e4-107">要求</span><span class="sxs-lookup"><span data-stu-id="004e4-107">Requirements</span></span>  
 <span data-ttu-id="004e4-108">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="004e4-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="004e4-109">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="004e4-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="004e4-110">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="004e4-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="004e4-111">**.NET framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="004e4-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
