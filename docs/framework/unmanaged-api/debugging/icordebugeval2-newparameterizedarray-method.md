---
title: "ICorDebugEval2::NewParameterizedArray 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICorDebugEval2.NewParameterizedArray
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEval2::NewParameterizedArray
helpviewer_keywords:
- ICorDebugEval2::NewParameterizedArray method [.NET Framework debugging]
- NewParameterizedArray method [.NET Framework debugging]
ms.assetid: 45efb8ba-c4de-4109-945f-e734d376b43c
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: a605276fac66e395d5663bacff727c235981a868
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugeval2newparameterizedarray-method"></a>ICorDebugEval2::NewParameterizedArray 方法
分配的指定的元素类型和维度的一个新数组。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT NewParameterizedArray(  
    [in] ICorDebugType          *pElementType,  
    [in] ULONG32                rank,  
    [in, size_is(rank)] ULONG32 dims[],  
    [in, size_is(rank)] ULONG32 lowBounds[]  
);  
```  
  
#### <a name="parameters"></a>参数  
 `pElementType`  
 [in]指向一个 ICorDebugType 对象，表示存储在数组中元素的类型的指针。  
  
 `rank`  
 [in]数组的维度数。 在.NET Framework 2.0 版中，此值必须为 1。  
  
 `dims`  
 [in]以字节为单位，每个维度的数组大小。  
  
 `lowBounds`  
 [in] 可选。 数组的每个维度的下限。 如果省略此值，每个维度假设下限为零。  
  
## <a name="remarks"></a>备注  
 数组的元素可能是泛型类型的实例。 始终在线程当前运行的应用程序域中创建数组。 在.NET Framework 2.0 中，值`rank`必须为 1。  
  
## <a name="requirements"></a>惠?  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** CorDebug.idl、 CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
