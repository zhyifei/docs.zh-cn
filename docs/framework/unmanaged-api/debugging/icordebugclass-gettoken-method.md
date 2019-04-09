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
ms.openlocfilehash: c4f33bb15a351be5fe8318dcc3339d429dec039e
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59183698"
---
# <a name="icordebugclassgettoken-method"></a><span data-ttu-id="a7abd-102">ICorDebugClass::GetToken 方法</span><span class="sxs-lookup"><span data-stu-id="a7abd-102">ICorDebugClass::GetToken Method</span></span>
<span data-ttu-id="a7abd-103">获取`TypeDef`元数据标记所引用的此类定义。</span><span class="sxs-lookup"><span data-stu-id="a7abd-103">Gets the `TypeDef` metadata token that references the definition of this class.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a7abd-104">语法</span><span class="sxs-lookup"><span data-stu-id="a7abd-104">Syntax</span></span>  
  
```  
HRESULT GetToken (  
    [out] mdTypeDef          *pTypeDef  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a7abd-105">参数</span><span class="sxs-lookup"><span data-stu-id="a7abd-105">Parameters</span></span>  
 `pTypeDef`  
 <span data-ttu-id="a7abd-106">[out]一个指向`mdTypeDef`引用此类定义的令牌。</span><span class="sxs-lookup"><span data-stu-id="a7abd-106">[out] A pointer to an `mdTypeDef` token that references the definition of this class.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a7abd-107">要求</span><span class="sxs-lookup"><span data-stu-id="a7abd-107">Requirements</span></span>  
 <span data-ttu-id="a7abd-108">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="a7abd-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a7abd-109">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a7abd-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a7abd-110">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a7abd-110">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="a7abd-111">.NET Framework 版本：</span><span class="sxs-lookup"><span data-stu-id="a7abd-111">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="a7abd-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="a7abd-112">See also</span></span>

- [<span data-ttu-id="a7abd-113">元数据接口</span><span class="sxs-lookup"><span data-stu-id="a7abd-113">Metadata Interfaces</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)
