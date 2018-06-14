---
title: ICorDebugAppDomain2::GetArrayOrPointerType 方法
ms.date: 03/30/2017
api_name:
- ICorDebugAppDomain2.GetArrayOrPointerType
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAppDomain2::GetArrayOrPointerType
helpviewer_keywords:
- GetArrayOrPointerType method [.NET Framework debugging]
- ICorDebugAppDomain2::GetArrayOrPointerType method [.NET Framework debugging]
ms.assetid: 97e493f5-3a62-4ec7-b42f-4af57bf71f57
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: cb3f0ca6d930b22f30fe9bbc5b5a04bf1e034f34
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33405820"
---
# <a name="icordebugappdomain2getarrayorpointertype-method"></a>ICorDebugAppDomain2::GetArrayOrPointerType 方法
获取指定的类型、 指针或对指定的类型引用的数组。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT GetArrayOrPointerType (  
    [in]  CorElementType    elementType,  
    [in]  ULONG32           nRank,  
    [in]  ICorDebugType     *pTypeArg,  
    [out] ICorDebugType     **ppType  
);  
```  
  
#### <a name="parameters"></a>参数  
 `elementType`  
 [in]CorElementType 枚举，指定 （数组、 指针或引用） 要创建的基础本机类型的值。  
  
 `nRank`  
 [in]数组的秩 （也就是说，多个维度）。 此值必须为 0，如果`elementType`指定指针或引用类型。  
  
 `pTypeArg`  
 [in]指针指向表示数组的类型的 ICorDebugType 对象、 指针或引用要创建。  
  
 `ppType`  
 [out]指向的地址的指针`ICorDebugType`对象表示构造的数组、 指针类型或引用类型。  
  
## <a name="remarks"></a>备注  
 值*elementType*必须是以下之一：  
  
-   ELEMENT_TYPE_PTR  
  
-   ELEMENT_TYPE_BYREF  
  
-   ELEMENT_TYPE_ARRAY 或 ELEMENT_TYPE_SZARRAY  
  
 如果值*elementType* ELEMENT_TYPE_PTR 或 ELEMENT_TYPE_BYREF， *nRank*必须为零。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** CorDebug.idl、 CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
