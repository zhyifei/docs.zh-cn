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
ms.openlocfilehash: f67bd427c83385b2433b9f2e97f0b54e3b29a76f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33401058"
---
# <a name="icordebugclassgettoken-method"></a><span data-ttu-id="67869-102">ICorDebugClass::GetToken 方法</span><span class="sxs-lookup"><span data-stu-id="67869-102">ICorDebugClass::GetToken Method</span></span>
<span data-ttu-id="67869-103">获取`TypeDef`引用此类定义的元数据标记。</span><span class="sxs-lookup"><span data-stu-id="67869-103">Gets the `TypeDef` metadata token that references the definition of this class.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="67869-104">语法</span><span class="sxs-lookup"><span data-stu-id="67869-104">Syntax</span></span>  
  
```  
HRESULT GetToken (  
    [out] mdTypeDef          *pTypeDef  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="67869-105">参数</span><span class="sxs-lookup"><span data-stu-id="67869-105">Parameters</span></span>  
 `pTypeDef`  
 <span data-ttu-id="67869-106">[out]指向的指针`mdTypeDef`引用此类定义的令牌。</span><span class="sxs-lookup"><span data-stu-id="67869-106">[out] A pointer to an `mdTypeDef` token that references the definition of this class.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="67869-107">要求</span><span class="sxs-lookup"><span data-stu-id="67869-107">Requirements</span></span>  
 <span data-ttu-id="67869-108">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="67869-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="67869-109">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="67869-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="67869-110">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="67869-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="67869-111">**.NET framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="67869-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="67869-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="67869-112">See Also</span></span>  
 [<span data-ttu-id="67869-113">元数据接口</span><span class="sxs-lookup"><span data-stu-id="67869-113">Metadata Interfaces</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)
