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
ms.openlocfilehash: b96c6ab8fb9065e1a08ad45a7f4482ef0b32788b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33418878"
---
# <a name="icordebugtypegetbase-method"></a><span data-ttu-id="9f199-102">ICorDebugType::GetBase 方法</span><span class="sxs-lookup"><span data-stu-id="9f199-102">ICorDebugType::GetBase Method</span></span>
<span data-ttu-id="9f199-103">获取的接口指针指向表示基类型，如果存在，表示此类型 ICorDebugType `ICorDebugType`。</span><span class="sxs-lookup"><span data-stu-id="9f199-103">Gets an interface pointer to an ICorDebugType that represents the base type, if one exists, of the type represented by this `ICorDebugType`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9f199-104">语法</span><span class="sxs-lookup"><span data-stu-id="9f199-104">Syntax</span></span>  
  
```  
HRESULT GetBase (  
    [out] ICorDebugType   **pBase  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="9f199-105">参数</span><span class="sxs-lookup"><span data-stu-id="9f199-105">Parameters</span></span>  
 `pBase`  
 <span data-ttu-id="9f199-106">[out]指向的地址的指针`ICorDebugType`表示基类型的对象。</span><span class="sxs-lookup"><span data-stu-id="9f199-106">[out] A pointer to the address of an `ICorDebugType` object that represents the base type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9f199-107">备注</span><span class="sxs-lookup"><span data-stu-id="9f199-107">Remarks</span></span>  
 <span data-ttu-id="9f199-108">查找类型的基类型可用于实现常见的调试器功能，例如打印出的对象或其父类的所有字段。</span><span class="sxs-lookup"><span data-stu-id="9f199-108">Looking up the base type for a type is useful to implement common debugger functionality, such as printing out all the fields of an object or its parent classes.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9f199-109">要求</span><span class="sxs-lookup"><span data-stu-id="9f199-109">Requirements</span></span>  
 <span data-ttu-id="9f199-110">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="9f199-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9f199-111">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9f199-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9f199-112">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9f199-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9f199-113">**.NET framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9f199-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
