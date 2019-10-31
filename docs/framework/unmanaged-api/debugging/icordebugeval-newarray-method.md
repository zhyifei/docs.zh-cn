---
title: ICorDebugEval::NewArray 方法
ms.date: 03/30/2017
api_name:
- ICorDebugEval.NewArray
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEval::NewArray
helpviewer_keywords:
- NewArray method [.NET Framework debugging]
- ICorDebugEval::NewArray method [.NET Framework debugging]
ms.assetid: cc79a67d-5368-434d-a943-209db90491b9
topic_type:
- apiref
ms.openlocfilehash: ca0844e4d2b1cad65266d58c6cda74de203d1758
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73137661"
---
# <a name="icordebugevalnewarray-method"></a>ICorDebugEval::NewArray 方法
分配指定元素类型和维度的新数组。  
  
 此方法在 .NET Framework 版本2.0 中已过时。 改[为使用 ICorDebugEval2：： NewParameterizedArray](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-newparameterizedarray-method.md) 。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT NewArray (  
    [in] CorElementType     elementType,  
    [in] ICorDebugClass     *pElementClass,  
    [in] ULONG32            rank,  
    [in, size_is(rank)] ULONG32 dims[],  
    [in, size_is(rank)] ULONG32 lowBounds[]  
);  
```  
  
## <a name="parameters"></a>参数  
 `elementType`  
 中CorElementType 枚举的一个值，该值指定数组的元素类型。  
  
 `pElementClass`  
 中指向 ICorDebugClass 对象的指针，该对象指定元素的类。 如果元素类型为基元类型，则此值可以为 null。  
  
 `rank`  
 中数组的维数。 在 .NET Framework 2.0 中，此值必须为1。  
  
 `dims`  
 中数组每个维度的大小（以字节为单位）。  
  
 `lowBounds`  
 [in] 可选。 数组的每个维度的下限。 如果省略此值，则假定每个维度的下限为零。  
  
## <a name="remarks"></a>备注  
 始终在当前执行线程的应用程序域中创建数组。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头**：CorDebug.idl、CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET Framework 版本：** 1.1、1。0
