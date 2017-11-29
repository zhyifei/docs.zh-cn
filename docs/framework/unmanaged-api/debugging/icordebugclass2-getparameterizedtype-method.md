---
title: "ICorDebugClass2::GetParameterizedType 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugClass2.GetParameterizedType
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugClass2::GetParameterizedType
helpviewer_keywords:
- GetParameterizedType method [.NET Framework debugging]
- ICorDebugClass2::GetParameterizedType method [.NET Framework debugging]
ms.assetid: 94b591c4-9302-4af2-a510-089496afb036
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: e0df76f43ad037a4681f985e99401cb8c7f5a2ce
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugclass2getparameterizedtype-method"></a>ICorDebugClass2::GetParameterizedType 方法
获取此类的类型声明。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT GetParameterizedType (  
    [in] CorElementType                      elementType,  
    [in] ULONG32                             nTypeArgs,  
    [in, size_is(nTypeArgs)] ICorDebugType  *ppTypeArgs[],  
    [out] ICorDebugType                    **ppType  
);  
```  
  
#### <a name="parameters"></a>参数  
 `elementType`  
 [in]CorElementType 枚举，指定此类的元素类型的值： 将此值设置为 ELEMENT_TYPE_VALUETYPE，如果此 ICorDebugClass2 表示值类型。 将此值设置为 ELEMENT_TYPE_CLASS，如果此`ICorDebugClass2`表示一个复杂类型。  
  
 `nTypeArgs`  
 [in]类型参数，如果该类型是泛型的数目。 类型参数 （如果有） 的数目必须匹配由类所需的数量。  
  
 `ppTypeArgs`  
 [in]一个指针数组，其中每个指向对象的表示类型参数。 如果此类是非泛型，则此值为 null。  
  
 `ppType`  
 [out]指向的地址的指针`ICorDebugType`表示类型声明的对象。 此对象是否等效于<xref:System.Type>在托管代码中的对象。  
  
## <a name="remarks"></a>备注  
 如果此类是非泛型的也就是说，如果它没有任何类型参数，`GetParameterizedType`只需获取对应于类的运行时类型对象。 `elementType`参数应设置为类的正确的元素类型： ELEMENT_TYPE_VALUETYPE 如果此类是值类型; 否则为 ELEMENT_TYPE_CLASS。  
  
 如果类接受类型参数 (例如， `ArrayList<T>`)，你可以使用`GetParameterizedType`如构造实例化类型的类型对象`ArrayList<int>`。  
  
## <a name="background-information"></a>背景信息  
 在.NET framework 1.0 和 1.1 版中，每种类型的元数据中无法直接映射到正在运行的进程中的类型。 因此，元数据类型和运行时类型也应正在运行的进程中有一种表示形式。 但是，在元数据中的一个泛型类型可以映射到的正在运行的进程中的类型的多个不同实例化。 例如，元数据类型`SortedList<K,V>`可以将映射到`SortedList<String, EmployeeRecord>`， `SortedList<Int32, String>`， `SortedList<String,Array<Int32>>`，依次类推。 因此，你需要处理类型实例化的方法。  
  
 .NET Framework 2.0 版引入了`ICorDebugType`接口。 对于泛型类型，`ICorDebugClass`或`ICorDebugClass2`对象表示未实例化的类型 (`SortedList<K,V>`)，和`ICorDebugType`对象表示的各种实例化的类型。 给定`ICorDebugClass`或`ICorDebugClass2`对象，你可以创建`ICorDebugType`通过调用任何实例化的对象`ICorDebugClass2::GetParameterizedType`方法。 你还可以创建`ICorDebugType`简单类型，如 Int32，或非泛型类型的对象。  
  
 引入`ICorDebugType`对象来表示一种类型的运行时概念产生连锁反应在整个 API。 以前所用的函数`ICorDebugClass`或`ICorDebugClass2`对象或者甚至`CorElementType`值现在普遍采用`ICorDebugType`对象。  
  
## <a name="requirements"></a>要求  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** CorDebug.idl、 CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
