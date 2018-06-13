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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: cfc8800915009912716ec2ed9044a633a8ad0582
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33401740"
---
# <a name="icordebugboxvaluegetobject-method"></a><span data-ttu-id="4b389-102">ICorDebugBoxValue::GetObject 方法</span><span class="sxs-lookup"><span data-stu-id="4b389-102">ICorDebugBoxValue::GetObject Method</span></span>
<span data-ttu-id="4b389-103">获取已装箱的值。</span><span class="sxs-lookup"><span data-stu-id="4b389-103">Gets the boxed value.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4b389-104">语法</span><span class="sxs-lookup"><span data-stu-id="4b389-104">Syntax</span></span>  
  
```  
HRESULT GetObject (  
    [out] ICorDebugObjectValue **ppObject  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="4b389-105">参数</span><span class="sxs-lookup"><span data-stu-id="4b389-105">Parameters</span></span>  
 `ppObject`  
 <span data-ttu-id="4b389-106">[out]指向一个 ICorDebugObjectValue 对象，表示装箱的值的地址的指针。</span><span class="sxs-lookup"><span data-stu-id="4b389-106">[out] A pointer to the address of an ICorDebugObjectValue object that represents the boxed value.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4b389-107">要求</span><span class="sxs-lookup"><span data-stu-id="4b389-107">Requirements</span></span>  
 <span data-ttu-id="4b389-108">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="4b389-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4b389-109">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4b389-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4b389-110">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4b389-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4b389-111">**.NET framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4b389-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
