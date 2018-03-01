---
title: "ICorDebugClass::GetToken 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICorDebugClass.GetToken
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugClass::GetToken
helpviewer_keywords:
- GetToken method, ICorDebugClass interface [.NET Framework debugging]
- ICorDebugClass::GetToken method [.NET Framework debugging]
ms.assetid: ee5c848a-eac4-4462-b07a-07ccd76a75df
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 408575c53feb81a2b273bd1064e2d3eaa37c4fb8
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugclassgettoken-method"></a><span data-ttu-id="63fee-102">ICorDebugClass::GetToken 方法</span><span class="sxs-lookup"><span data-stu-id="63fee-102">ICorDebugClass::GetToken Method</span></span>
<span data-ttu-id="63fee-103">获取`TypeDef`引用此类定义的元数据标记。</span><span class="sxs-lookup"><span data-stu-id="63fee-103">Gets the `TypeDef` metadata token that references the definition of this class.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="63fee-104">语法</span><span class="sxs-lookup"><span data-stu-id="63fee-104">Syntax</span></span>  
  
```  
HRESULT GetToken (  
    [out] mdTypeDef          *pTypeDef  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="63fee-105">参数</span><span class="sxs-lookup"><span data-stu-id="63fee-105">Parameters</span></span>  
 `pTypeDef`  
 <span data-ttu-id="63fee-106">[out]指向的指针`mdTypeDef`引用此类定义的令牌。</span><span class="sxs-lookup"><span data-stu-id="63fee-106">[out] A pointer to an `mdTypeDef` token that references the definition of this class.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="63fee-107">惠?</span><span class="sxs-lookup"><span data-stu-id="63fee-107">Requirements</span></span>  
 <span data-ttu-id="63fee-108">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="63fee-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="63fee-109">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="63fee-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="63fee-110">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="63fee-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="63fee-111">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="63fee-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="63fee-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="63fee-112">See Also</span></span>  
 [<span data-ttu-id="63fee-113">元数据接口</span><span class="sxs-lookup"><span data-stu-id="63fee-113">Metadata Interfaces</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)
