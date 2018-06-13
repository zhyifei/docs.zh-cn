---
title: ICorDebugGenericValue::GetValue 方法
ms.date: 03/30/2017
api_name:
- ICorDebugGenericValue.GetValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugGenericValue::GetValue
helpviewer_keywords:
- ICorDebugGenericValue::GetValue method [.NET Framework debugging]
- GetValue method, ICorDebugGenericValue interface [.NET Framework debugging]
ms.assetid: 4e95d7cb-144d-4ccf-8a69-d605f4744be2
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a6d30a9f03d8717486be7cd89bb182d350a82df7
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33411631"
---
# <a name="icordebuggenericvaluegetvalue-method"></a><span data-ttu-id="0c67b-102">ICorDebugGenericValue::GetValue 方法</span><span class="sxs-lookup"><span data-stu-id="0c67b-102">ICorDebugGenericValue::GetValue Method</span></span>
<span data-ttu-id="0c67b-103">将此泛型值复制到指定的缓冲区。</span><span class="sxs-lookup"><span data-stu-id="0c67b-103">Copies the value of this generic into the specified buffer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0c67b-104">语法</span><span class="sxs-lookup"><span data-stu-id="0c67b-104">Syntax</span></span>  
  
```  
HRESULT GetValue (  
    [out] void     *pTo  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="0c67b-105">参数</span><span class="sxs-lookup"><span data-stu-id="0c67b-105">Parameters</span></span>  
 `pTo`  
 <span data-ttu-id="0c67b-106">[out]指向此 ICorDebugGenericValue 对象表示的值的指针。</span><span class="sxs-lookup"><span data-stu-id="0c67b-106">[out] A pointer to the value that is represented by this ICorDebugGenericValue object.</span></span> <span data-ttu-id="0c67b-107">值可以是简单类型或引用类型 （即，指针）。</span><span class="sxs-lookup"><span data-stu-id="0c67b-107">The value may be a simple type or a reference type (that is, a pointer).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0c67b-108">要求</span><span class="sxs-lookup"><span data-stu-id="0c67b-108">Requirements</span></span>  
 <span data-ttu-id="0c67b-109">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="0c67b-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0c67b-110">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0c67b-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0c67b-111">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0c67b-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0c67b-112">**.NET framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0c67b-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
