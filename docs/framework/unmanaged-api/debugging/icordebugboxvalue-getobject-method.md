---
title: ICorDebugBoxValue::GetObject 方法
ms.date: 03/30/2017
api_name:
- ICorDebugBoxValue.GetObject
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugBoxValue::GetObject
helpviewer_keywords:
- ICorDebugBoxValue::GetObject method [.NET Framework debugging]
- GetObject method, ICorDebugBoxValue interface [.NET Framework debugging]
ms.assetid: 3a867a5b-bf94-493f-a4f5-b28685cf5325
topic_type:
- apiref
ms.openlocfilehash: 475cc6c688262f318aa7f844b975ad69fa80bbe9
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73122820"
---
# <a name="icordebugboxvaluegetobject-method"></a><span data-ttu-id="6a836-102">ICorDebugBoxValue::GetObject 方法</span><span class="sxs-lookup"><span data-stu-id="6a836-102">ICorDebugBoxValue::GetObject Method</span></span>
<span data-ttu-id="6a836-103">获取装箱的值。</span><span class="sxs-lookup"><span data-stu-id="6a836-103">Gets the boxed value.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6a836-104">语法</span><span class="sxs-lookup"><span data-stu-id="6a836-104">Syntax</span></span>  
  
```cpp  
HRESULT GetObject (  
    [out] ICorDebugObjectValue **ppObject  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6a836-105">参数</span><span class="sxs-lookup"><span data-stu-id="6a836-105">Parameters</span></span>  
 `ppObject`  
 <span data-ttu-id="6a836-106">弄指向表示装箱值的 ICorDebugObjectValue 对象地址的指针。</span><span class="sxs-lookup"><span data-stu-id="6a836-106">[out] A pointer to the address of an ICorDebugObjectValue object that represents the boxed value.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6a836-107">要求</span><span class="sxs-lookup"><span data-stu-id="6a836-107">Requirements</span></span>  
 <span data-ttu-id="6a836-108">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="6a836-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6a836-109">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6a836-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6a836-110">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6a836-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6a836-111">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6a836-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
