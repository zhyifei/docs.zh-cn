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
ms.openlocfilehash: 3433f5f69927afb501c2596571f138e3a69fabb6
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2020
ms.locfileid: "82894114"
---
# <a name="icordebugclassgettoken-method"></a><span data-ttu-id="ed6e7-102">ICorDebugClass::GetToken 方法</span><span class="sxs-lookup"><span data-stu-id="ed6e7-102">ICorDebugClass::GetToken Method</span></span>
<span data-ttu-id="ed6e7-103">获取引用`TypeDef`此类的定义的元数据标记。</span><span class="sxs-lookup"><span data-stu-id="ed6e7-103">Gets the `TypeDef` metadata token that references the definition of this class.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ed6e7-104">语法</span><span class="sxs-lookup"><span data-stu-id="ed6e7-104">Syntax</span></span>  
  
```cpp  
HRESULT GetToken (  
    [out] mdTypeDef          *pTypeDef  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ed6e7-105">参数</span><span class="sxs-lookup"><span data-stu-id="ed6e7-105">Parameters</span></span>  
 `pTypeDef`  
 <span data-ttu-id="ed6e7-106">弄指向引用此类`mdTypeDef`的定义的标记的指针。</span><span class="sxs-lookup"><span data-stu-id="ed6e7-106">[out] A pointer to an `mdTypeDef` token that references the definition of this class.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ed6e7-107">要求</span><span class="sxs-lookup"><span data-stu-id="ed6e7-107">Requirements</span></span>  
 <span data-ttu-id="ed6e7-108">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="ed6e7-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ed6e7-109">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ed6e7-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ed6e7-110">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ed6e7-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ed6e7-111">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ed6e7-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ed6e7-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ed6e7-112">See also</span></span>

- [<span data-ttu-id="ed6e7-113">元数据接口</span><span class="sxs-lookup"><span data-stu-id="ed6e7-113">Metadata Interfaces</span></span>](../metadata/metadata-interfaces.md)
