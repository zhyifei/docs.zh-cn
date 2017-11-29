---
title: "ICorDebugStringValue::GetLength 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugStringValue.GetLength
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugStringValue::GetLength
helpviewer_keywords:
- ICorDebugStringValue::GetLength method [.NET Framework debugging]
- GetLength method [.NET Framework debugging]
ms.assetid: a1ebfc69-46a6-4225-8788-b7cfb2f15e1d
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: c072e7420e400e6402c8697eefc62c658c590261
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugstringvaluegetlength-method"></a><span data-ttu-id="4d841-102">ICorDebugStringValue::GetLength 方法</span><span class="sxs-lookup"><span data-stu-id="4d841-102">ICorDebugStringValue::GetLength Method</span></span>
<span data-ttu-id="4d841-103">获取此 ICorDebugStringValue 引用字符串中的字符数。</span><span class="sxs-lookup"><span data-stu-id="4d841-103">Gets the number of characters in the string referenced by this ICorDebugStringValue.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4d841-104">语法</span><span class="sxs-lookup"><span data-stu-id="4d841-104">Syntax</span></span>  
  
```  
HRESULT GetLength (  
    [out] ULONG32   *pcchString  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="4d841-105">参数</span><span class="sxs-lookup"><span data-stu-id="4d841-105">Parameters</span></span>  
 `pcchString`  
 <span data-ttu-id="4d841-106">[out]指向一个值，指定引用的字符串的长度的指针`ICorDebugStringValue`对象。</span><span class="sxs-lookup"><span data-stu-id="4d841-106">[out] A pointer to a value that specifies the length of the string referenced by this `ICorDebugStringValue` object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4d841-107">要求</span><span class="sxs-lookup"><span data-stu-id="4d841-107">Requirements</span></span>  
 <span data-ttu-id="4d841-108">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="4d841-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4d841-109">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4d841-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4d841-110">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4d841-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4d841-111">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4d841-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
