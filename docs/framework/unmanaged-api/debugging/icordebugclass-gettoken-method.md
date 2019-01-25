---
title: ICorDebugClass::GetToken 方法
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d6dc245a53c9ec7cbe56e20313abc4269e33f45c
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54582313"
---
# <a name="icordebugclassgettoken-method"></a><span data-ttu-id="2a96a-102">ICorDebugClass::GetToken 方法</span><span class="sxs-lookup"><span data-stu-id="2a96a-102">ICorDebugClass::GetToken Method</span></span>
<span data-ttu-id="2a96a-103">获取`TypeDef`元数据标记所引用的此类定义。</span><span class="sxs-lookup"><span data-stu-id="2a96a-103">Gets the `TypeDef` metadata token that references the definition of this class.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2a96a-104">语法</span><span class="sxs-lookup"><span data-stu-id="2a96a-104">Syntax</span></span>  
  
```  
HRESULT GetToken (  
    [out] mdTypeDef          *pTypeDef  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="2a96a-105">参数</span><span class="sxs-lookup"><span data-stu-id="2a96a-105">Parameters</span></span>  
 `pTypeDef`  
 <span data-ttu-id="2a96a-106">[out]一个指向`mdTypeDef`引用此类定义的令牌。</span><span class="sxs-lookup"><span data-stu-id="2a96a-106">[out] A pointer to an `mdTypeDef` token that references the definition of this class.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2a96a-107">要求</span><span class="sxs-lookup"><span data-stu-id="2a96a-107">Requirements</span></span>  
 <span data-ttu-id="2a96a-108">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="2a96a-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2a96a-109">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2a96a-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2a96a-110">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2a96a-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2a96a-111">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2a96a-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2a96a-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="2a96a-112">See also</span></span>
- [<span data-ttu-id="2a96a-113">元数据接口</span><span class="sxs-lookup"><span data-stu-id="2a96a-113">Metadata Interfaces</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)
