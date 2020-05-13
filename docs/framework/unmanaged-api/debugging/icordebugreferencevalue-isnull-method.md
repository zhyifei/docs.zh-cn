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
ms.openlocfilehash: e8b778c0880040f5ffd639a445fd5663ce493219
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/13/2020
ms.locfileid: "83379087"
---
# <a name="icordebugreferencevalueisnull-method"></a><span data-ttu-id="e5c14-102">ICorDebugReferenceValue::IsNull 方法</span><span class="sxs-lookup"><span data-stu-id="e5c14-102">ICorDebugReferenceValue::IsNull Method</span></span>
<span data-ttu-id="e5c14-103">获取一个值，该值指示此 ICorDebugReferenceValue 是否为 null 值，在这种情况下，不 `ICorDebugReferenceValue` 指向对象。</span><span class="sxs-lookup"><span data-stu-id="e5c14-103">Gets a value that indicates whether this ICorDebugReferenceValue is a null value, in which case the `ICorDebugReferenceValue` does not point to an object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e5c14-104">语法</span><span class="sxs-lookup"><span data-stu-id="e5c14-104">Syntax</span></span>  
  
```cpp  
HRESULT IsNull (  
    [out] BOOL   *pbNull  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e5c14-105">参数</span><span class="sxs-lookup"><span data-stu-id="e5c14-105">Parameters</span></span>  
 `pbNull`  
 <span data-ttu-id="e5c14-106">弄`true`如果此对象为 null，则为指向布尔值的指针 `ICorDebugReferenceValue` ; 否则为 `pbNull` `false` 。</span><span class="sxs-lookup"><span data-stu-id="e5c14-106">[out] A pointer to a Boolean value that is `true` if this `ICorDebugReferenceValue` object is null; otherwise, `pbNull` is `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e5c14-107">要求</span><span class="sxs-lookup"><span data-stu-id="e5c14-107">Requirements</span></span>  
 <span data-ttu-id="e5c14-108">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="e5c14-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e5c14-109">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e5c14-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e5c14-110">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e5c14-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e5c14-111">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e5c14-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
