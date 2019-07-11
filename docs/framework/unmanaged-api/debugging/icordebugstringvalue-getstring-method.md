---
title: ICorDebugStringValue::GetString 方法
ms.date: 03/30/2017
api_name:
- ICorDebugStringValue.GetString
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugStringValue::GetString
helpviewer_keywords:
- ICorDebugStringValue::GetString method [.NET Framework debugging]
- GetString method, ICorDebugStringValue interface [.NET Framework debugging]
ms.assetid: 2b94bda7-09ee-435d-91b9-c4e31af1896c
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 77c88786befb92960f4cfa4a960cbfc624318b26
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/10/2019
ms.locfileid: "67771590"
---
# <a name="icordebugstringvaluegetstring-method"></a><span data-ttu-id="dc209-102">ICorDebugStringValue::GetString 方法</span><span class="sxs-lookup"><span data-stu-id="dc209-102">ICorDebugStringValue::GetString Method</span></span>
<span data-ttu-id="dc209-103">获取此 ICorDebugStringValue 引用的字符串。</span><span class="sxs-lookup"><span data-stu-id="dc209-103">Gets the string referenced by this ICorDebugStringValue.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dc209-104">语法</span><span class="sxs-lookup"><span data-stu-id="dc209-104">Syntax</span></span>  
  
```cpp  
HRESULT GetString (  
    [in] ULONG32    cchString,  
    [out] ULONG32   *pcchString,  
    [out, size_is(cchString), length_is(*pcchString)]   
        WCHAR       szString[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="dc209-105">参数</span><span class="sxs-lookup"><span data-stu-id="dc209-105">Parameters</span></span>  
 `cchString`  
 <span data-ttu-id="dc209-106">[in] `szString` 数组的大小。</span><span class="sxs-lookup"><span data-stu-id="dc209-106">[in] The size of the `szString` array.</span></span>  
  
 `pcchString`  
 <span data-ttu-id="dc209-107">[out]指向中返回的字符数的`szString`数组。</span><span class="sxs-lookup"><span data-stu-id="dc209-107">[out] A pointer to the number of characters returned in the `szString` array.</span></span>  
  
 `szString`  
 <span data-ttu-id="dc209-108">[out]一个数组，将检索到的字符串存储。</span><span class="sxs-lookup"><span data-stu-id="dc209-108">[out] An array that stores the retrieved string.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dc209-109">要求</span><span class="sxs-lookup"><span data-stu-id="dc209-109">Requirements</span></span>  
 <span data-ttu-id="dc209-110">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="dc209-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dc209-111">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="dc209-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="dc209-112">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="dc209-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="dc209-113">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dc209-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
