---
title: ICorDebugILFrame2::EnumerateTypeParameters 方法
ms.date: 03/30/2017
api_name:
- ICorDebugILFrame2.EnumerateTypeParameters
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugILFrame2::EnumerateTypeParameters
helpviewer_keywords:
- EnumerateTypeParameters method, ICorDebugILFrame2 interface [.NET Framework debugging]
- ICorDebugILFrame2::EnumerateTypeParameters method [.NET Framework debugging]
ms.assetid: 722d0d74-e0df-491f-98c4-62d501dfaf6f
topic_type:
- apiref
ms.openlocfilehash: 9020fed83b1c57cae3cc492872a279afb0195983
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/12/2020
ms.locfileid: "83205177"
---
# <a name="icordebugilframe2enumeratetypeparameters-method"></a>ICorDebugILFrame2::EnumerateTypeParameters 方法
获取一个 ICorDebugTypeEnum 对象，该对象包含 <xref:System.Type> 此帧中的参数。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT EnumerateTypeParameters (  
    [out] ICorDebugTypeEnum    **ppTyParEnum  
);  
```  
  
## <a name="parameters"></a>参数  
 `ppTyParEnum`  
 指向允许枚举类型参数的 ICorDebugTypeEnum 接口对象地址的指针。  
  
 类型参数列表包含类类型参数（如果有），后跟方法类型参数（如果有）。  
  
## <a name="remarks"></a>备注  
 使用[IMetaDataImport2：： EnumGenericParams](../metadata/imetadataimport2-enumgenericparams-method.md)方法确定此列表包含多少类类型参数和方法类型参数。  
  
 类型参数并非始终可用。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。  
  
 **标头**：CorDebug.idl、CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
