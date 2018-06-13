---
title: ICorDebugStringValue::GetLength 方法
ms.date: 03/30/2017
api_name:
- ICorDebugStringValue.GetLength
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugStringValue::GetLength
helpviewer_keywords:
- ICorDebugStringValue::GetLength method [.NET Framework debugging]
- GetLength method [.NET Framework debugging]
ms.assetid: a1ebfc69-46a6-4225-8788-b7cfb2f15e1d
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e62539304817432fcab8f3e0958e5a70b371b83d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33416941"
---
# <a name="icordebugstringvaluegetlength-method"></a><span data-ttu-id="21930-102">ICorDebugStringValue::GetLength 方法</span><span class="sxs-lookup"><span data-stu-id="21930-102">ICorDebugStringValue::GetLength Method</span></span>
<span data-ttu-id="21930-103">获取此 ICorDebugStringValue 引用字符串中的字符数。</span><span class="sxs-lookup"><span data-stu-id="21930-103">Gets the number of characters in the string referenced by this ICorDebugStringValue.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="21930-104">语法</span><span class="sxs-lookup"><span data-stu-id="21930-104">Syntax</span></span>  
  
```  
HRESULT GetLength (  
    [out] ULONG32   *pcchString  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="21930-105">参数</span><span class="sxs-lookup"><span data-stu-id="21930-105">Parameters</span></span>  
 `pcchString`  
 <span data-ttu-id="21930-106">[out]指向一个值，指定引用的字符串的长度的指针`ICorDebugStringValue`对象。</span><span class="sxs-lookup"><span data-stu-id="21930-106">[out] A pointer to a value that specifies the length of the string referenced by this `ICorDebugStringValue` object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="21930-107">要求</span><span class="sxs-lookup"><span data-stu-id="21930-107">Requirements</span></span>  
 <span data-ttu-id="21930-108">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="21930-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="21930-109">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="21930-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="21930-110">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="21930-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="21930-111">**.NET framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="21930-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
