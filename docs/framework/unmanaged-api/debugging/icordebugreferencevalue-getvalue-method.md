---
title: ICorDebugReferenceValue::GetValue 方法
ms.date: 03/30/2017
api_name:
- ICorDebugReferenceValue.GetValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugReferenceValue::GetValue
helpviewer_keywords:
- GetValue method, ICorDebugReferenceValue interface [.NET Framework debugging]
- ICorDebugReferenceValue::GetValue method [.NET Framework debugging]
ms.assetid: 5da07f99-6c70-46ec-b997-5ab6fb7106cd
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 92df7bbcc2c391dd28f4075a97595762403d8def
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33416310"
---
# <a name="icordebugreferencevaluegetvalue-method"></a><span data-ttu-id="75e69-102">ICorDebugReferenceValue::GetValue 方法</span><span class="sxs-lookup"><span data-stu-id="75e69-102">ICorDebugReferenceValue::GetValue Method</span></span>
<span data-ttu-id="75e69-103">获取被引用的对象的当前内存地址。</span><span class="sxs-lookup"><span data-stu-id="75e69-103">Gets the current memory address of the referenced object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="75e69-104">语法</span><span class="sxs-lookup"><span data-stu-id="75e69-104">Syntax</span></span>  
  
```  
HRESULT GetValue (  
    [out] CORDB_ADDRESS   *pValue  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="75e69-105">参数</span><span class="sxs-lookup"><span data-stu-id="75e69-105">Parameters</span></span>  
 `pValue`  
 <span data-ttu-id="75e69-106">[out]指向的指针`CORDB_ADDRESS`值，该值指定此 ICorDebugReferenceValue 对象所指向的对象的地址。</span><span class="sxs-lookup"><span data-stu-id="75e69-106">[out] A pointer to a `CORDB_ADDRESS` value that specifies the address of the object to which this ICorDebugReferenceValue object points.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="75e69-107">要求</span><span class="sxs-lookup"><span data-stu-id="75e69-107">Requirements</span></span>  
 <span data-ttu-id="75e69-108">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="75e69-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="75e69-109">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="75e69-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="75e69-110">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="75e69-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="75e69-111">**.NET framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="75e69-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
