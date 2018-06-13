---
title: ICorDebugReferenceValue::IsNull 方法
ms.date: 03/30/2017
api_name:
- ICorDebugReferenceValue.IsNull
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugReferenceValue::IsNull
helpviewer_keywords:
- IsNull method, ICorDebugReferenceValue interface [.NET Framework debugging]
- ICorDebugReferenceValue::IsNull method [.NET Framework debugging]
ms.assetid: 99e8c8d7-a1c0-47c8-9dbd-03e0b2bcb4d5
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2c82c72350931bf3aed8ec6699cd0af834798e92
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33417210"
---
# <a name="icordebugreferencevalueisnull-method"></a><span data-ttu-id="51d89-102">ICorDebugReferenceValue::IsNull 方法</span><span class="sxs-lookup"><span data-stu-id="51d89-102">ICorDebugReferenceValue::IsNull Method</span></span>
<span data-ttu-id="51d89-103">获取一个值，该值指示此 ICorDebugReferenceValue 是否为空值，在这种情况下`ICorDebugReferenceValue`不指向的对象。</span><span class="sxs-lookup"><span data-stu-id="51d89-103">Gets a value that indicates whether this ICorDebugReferenceValue is a null value, in which case the `ICorDebugReferenceValue` does not point to an object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="51d89-104">语法</span><span class="sxs-lookup"><span data-stu-id="51d89-104">Syntax</span></span>  
  
```  
HRESULT IsNull (  
    [out] BOOL   *pbNull  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="51d89-105">参数</span><span class="sxs-lookup"><span data-stu-id="51d89-105">Parameters</span></span>  
 `pbNull`  
 <span data-ttu-id="51d89-106">[out]一个布尔值，是一个指向`true`如果此`ICorDebugReferenceValue`对象为空; 否则为`pbNull`是`false`。</span><span class="sxs-lookup"><span data-stu-id="51d89-106">[out] A pointer to a Boolean value that is `true` if this `ICorDebugReferenceValue` object is null; otherwise, `pbNull` is `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="51d89-107">要求</span><span class="sxs-lookup"><span data-stu-id="51d89-107">Requirements</span></span>  
 <span data-ttu-id="51d89-108">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="51d89-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="51d89-109">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="51d89-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="51d89-110">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="51d89-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="51d89-111">**.NET framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="51d89-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
