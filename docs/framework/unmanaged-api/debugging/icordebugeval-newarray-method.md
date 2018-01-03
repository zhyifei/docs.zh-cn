---
title: "ICorDebugEval::NewArray 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugEval.NewArray
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugEval::NewArray
helpviewer_keywords:
- NewArray method [.NET Framework debugging]
- ICorDebugEval::NewArray method [.NET Framework debugging]
ms.assetid: cc79a67d-5368-434d-a943-209db90491b9
topic_type: apiref
caps.latest.revision: "19"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: f9116c2ee7edbc39d203728909ce37e963c896fc
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugevalnewarray-method"></a>ICorDebugEval::NewArray 方法
分配的指定的元素类型和维度的一个新数组。  
  
 此方法是.NET Framework 2.0 版中过时。 使用[icordebugeval2:: Newparameterizedarray](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-newparameterizedarray-method.md)相反。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT NewArray (  
    [in] CorElementType     elementType,  
    [in] ICorDebugClass     *pElementClass,  
    [in] ULONG32            rank,  
    [in, size_is(rank)] ULONG32 dims[],  
    [in, size_is(rank)] ULONG32 lowBounds[]  
);  
```  
  
#### <a name="parameters"></a>参数  
 `elementType`  
 [in]CorElementType 枚举，指定数组的元素类型的值。  
  
 `pElementClass`  
 [in]指向一个指定元素的类的 ICorDebugClass 对象的指针。 此值可能为 null 的基元类型的元素类型时。  
  
 `rank`  
 [in]数组的维度数。 在.NET Framework 2.0 中，此值必须为 1。  
  
 `dims`  
 [in]以字节为单位，每个维度的数组大小。  
  
 `lowBounds`  
 [in] 可选。 数组的每个维度的下限。 如果省略此值，每个维度假设下限为零。  
  
## <a name="remarks"></a>备注  
 始终在线程当前执行的应用程序域中创建数组。  
  
## <a name="requirements"></a>惠?  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** CorDebug.idl、 CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET framework 版本：** 1.1、 1.0
