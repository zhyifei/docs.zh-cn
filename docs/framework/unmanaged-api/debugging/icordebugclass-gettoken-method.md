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
ms.openlocfilehash: 6964c931307a40f384ad8a8e355cab0aad575ec6
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73125776"
---
# <a name="icordebugclassgettoken-method"></a><span data-ttu-id="90fb3-102">ICorDebugClass::GetToken 方法</span><span class="sxs-lookup"><span data-stu-id="90fb3-102">ICorDebugClass::GetToken Method</span></span>
<span data-ttu-id="90fb3-103">获取引用此类的定义的 `TypeDef` 元数据标记。</span><span class="sxs-lookup"><span data-stu-id="90fb3-103">Gets the `TypeDef` metadata token that references the definition of this class.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="90fb3-104">语法</span><span class="sxs-lookup"><span data-stu-id="90fb3-104">Syntax</span></span>  
  
```cpp  
HRESULT GetToken (  
    [out] mdTypeDef          *pTypeDef  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="90fb3-105">参数</span><span class="sxs-lookup"><span data-stu-id="90fb3-105">Parameters</span></span>  
 `pTypeDef`  
 <span data-ttu-id="90fb3-106">弄指向引用此类的定义的 `mdTypeDef` 标记的指针。</span><span class="sxs-lookup"><span data-stu-id="90fb3-106">[out] A pointer to an `mdTypeDef` token that references the definition of this class.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="90fb3-107">要求</span><span class="sxs-lookup"><span data-stu-id="90fb3-107">Requirements</span></span>  
 <span data-ttu-id="90fb3-108">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="90fb3-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="90fb3-109">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="90fb3-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="90fb3-110">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="90fb3-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="90fb3-111">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="90fb3-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="90fb3-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="90fb3-112">See also</span></span>

- [<span data-ttu-id="90fb3-113">元数据接口</span><span class="sxs-lookup"><span data-stu-id="90fb3-113">Metadata Interfaces</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)
