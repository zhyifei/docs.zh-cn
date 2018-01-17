---
title: "ICorDebugType::EnumerateTypeParameters 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugType.EnumerateTypeParameters
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugType::EnumerateTypeParameters
helpviewer_keywords:
- EnumerateTypeParameters method, ICorDebugType interface [.NET Framework debugging]
- ICorDebugType::EnumerateTypeParameters method [.NET Framework debugging]
ms.assetid: 1ee1f6e6-1bd7-4ebb-83b8-ff9a08ca03de
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: d4b864b2b5fd4f2a6ed03218ce6e7b6f3bf62202
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugtypeenumeratetypeparameters-method"></a>ICorDebugType::EnumerateTypeParameters 方法
获取的接口指针指向包含 ICorDebugTypeEnum<xref:System.Type>参数的此 ICorDebugType 所引用的类。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT EnumerateTypeParameters (  
    [out] ICorDebugTypeEnum   **ppTyParEnum  
);  
```  
  
#### <a name="parameters"></a>参数  
 `ppTyParEnum`  
 [out]指向的地址的指针`ICorDebugTypeEnum`包含类型的参数。  
  
## <a name="remarks"></a>备注  
 你可以使用`EnumerateTypeParameters`如果返回 CorElementType 值[icordebugtype:: Gettype](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-gettype-method.md) ELEMENT_TYPE_CLASS、 ELEMENT_TYPE_VALUETYPE、 ELEMENT_TYPE_ARRAY、 ELEMENT_TYPE_SZARRAY、 ELEMENT_TYPE_BYREF、 ELEMENT_TYPE_PTR 或 ELEMENT_TYPE_FNPTR。 参数和它们的顺序的数量取决于的类型：  
  
-   ELEMENT_TYPE_CLASS 或 ELEMENT_TYPE_VALUETYPE： 中包含的类型参数的数目`ICorDebugTypeEnum`，此方法返回时，将取决于相应的类的形参类型参数的数目。 例如，如果类型为`class Dict<String,int32>`，然后`EnumerateTypeParameters`将返回`ICorDebugTypeEnum`，其中包含表示的对象`String`和`int32`序列中。  
  
-   ELEMENT_TYPE_FNPTR: 中包含的类型参数数目`ICorDebugTypeEnum`将是一个大于函数接受参数的数目。 中包含的第一个类型参数`ICorDebugTypeEnum`是该函数的返回类型和后面的类型参数是函数的参数。  
  
-   ELEMENT_TYPE_ARRAY、 ELEMENT_TYPE_SZARRAY、 ELEMENT_TYPE_BYREF 或 ELEMENT_TYPE_PTR： 将返回一个类型参数。 例如，如果类型是数组类型，如`int32[]`，`EnumerateTypeParameters`将返回`ICorDebugTypeEnum`包含对象，表示`int32`。  
  
## <a name="requirements"></a>惠?  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** CorDebug.idl、 CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
