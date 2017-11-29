---
title: "ICorDebugType::GetBase 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugType.GetBase
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugType::GetBase
helpviewer_keywords:
- ICorDebugType::GetBase method [.NET Framework debugging]
- GetBase method [.NET Framework debugging]
ms.assetid: f24e1af9-c220-4f79-ae62-4153ec17ea81
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: de00e519b43d486e70d5ed8165eed01b59d6e725
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugtypegetbase-method"></a><span data-ttu-id="1fb86-102">ICorDebugType::GetBase 方法</span><span class="sxs-lookup"><span data-stu-id="1fb86-102">ICorDebugType::GetBase Method</span></span>
<span data-ttu-id="1fb86-103">获取的接口指针指向表示基类型，如果存在，表示此类型 ICorDebugType `ICorDebugType`。</span><span class="sxs-lookup"><span data-stu-id="1fb86-103">Gets an interface pointer to an ICorDebugType that represents the base type, if one exists, of the type represented by this `ICorDebugType`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1fb86-104">语法</span><span class="sxs-lookup"><span data-stu-id="1fb86-104">Syntax</span></span>  
  
```  
HRESULT GetBase (  
    [out] ICorDebugType   **pBase  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="1fb86-105">参数</span><span class="sxs-lookup"><span data-stu-id="1fb86-105">Parameters</span></span>  
 `pBase`  
 <span data-ttu-id="1fb86-106">[out]指向的地址的指针`ICorDebugType`表示基类型的对象。</span><span class="sxs-lookup"><span data-stu-id="1fb86-106">[out] A pointer to the address of an `ICorDebugType` object that represents the base type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1fb86-107">备注</span><span class="sxs-lookup"><span data-stu-id="1fb86-107">Remarks</span></span>  
 <span data-ttu-id="1fb86-108">查找类型的基类型可用于实现常见的调试器功能，例如打印出的对象或其父类的所有字段。</span><span class="sxs-lookup"><span data-stu-id="1fb86-108">Looking up the base type for a type is useful to implement common debugger functionality, such as printing out all the fields of an object or its parent classes.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1fb86-109">要求</span><span class="sxs-lookup"><span data-stu-id="1fb86-109">Requirements</span></span>  
 <span data-ttu-id="1fb86-110">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="1fb86-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1fb86-111">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="1fb86-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1fb86-112">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1fb86-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1fb86-113">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1fb86-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
