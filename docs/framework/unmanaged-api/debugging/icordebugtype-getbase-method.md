---
title: ICorDebugType::GetBase 方法
ms.date: 03/30/2017
api_name:
- ICorDebugType.GetBase
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugType::GetBase
helpviewer_keywords:
- ICorDebugType::GetBase method [.NET Framework debugging]
- GetBase method [.NET Framework debugging]
ms.assetid: f24e1af9-c220-4f79-ae62-4153ec17ea81
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1d04bc67013a2227f295ac3a41be027b9f9b04e2
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61946300"
---
# <a name="icordebugtypegetbase-method"></a><span data-ttu-id="f22f2-102">ICorDebugType::GetBase 方法</span><span class="sxs-lookup"><span data-stu-id="f22f2-102">ICorDebugType::GetBase Method</span></span>
<span data-ttu-id="f22f2-103">如果存在，这表示的类型的表示基类型，ICorDebugType 到获取的接口指针`ICorDebugType`。</span><span class="sxs-lookup"><span data-stu-id="f22f2-103">Gets an interface pointer to an ICorDebugType that represents the base type, if one exists, of the type represented by this `ICorDebugType`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f22f2-104">语法</span><span class="sxs-lookup"><span data-stu-id="f22f2-104">Syntax</span></span>  
  
```  
HRESULT GetBase (  
    [out] ICorDebugType   **pBase  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f22f2-105">参数</span><span class="sxs-lookup"><span data-stu-id="f22f2-105">Parameters</span></span>  
 `pBase`  
 <span data-ttu-id="f22f2-106">[out]指向的地址的指针`ICorDebugType`表示基类型的对象。</span><span class="sxs-lookup"><span data-stu-id="f22f2-106">[out] A pointer to the address of an `ICorDebugType` object that represents the base type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f22f2-107">备注</span><span class="sxs-lookup"><span data-stu-id="f22f2-107">Remarks</span></span>  
 <span data-ttu-id="f22f2-108">查找一种类型的基类型可用于实现常见的调试器功能，例如打印出的对象或其父类的所有字段。</span><span class="sxs-lookup"><span data-stu-id="f22f2-108">Looking up the base type for a type is useful to implement common debugger functionality, such as printing out all the fields of an object or its parent classes.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f22f2-109">要求</span><span class="sxs-lookup"><span data-stu-id="f22f2-109">Requirements</span></span>  
 <span data-ttu-id="f22f2-110">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="f22f2-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f22f2-111">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f22f2-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f22f2-112">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f22f2-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f22f2-113">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f22f2-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
