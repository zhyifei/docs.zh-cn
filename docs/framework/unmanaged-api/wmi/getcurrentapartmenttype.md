---
title: "GetCurrentApartmentType 函数 （非托管 API 参考）"
description: "GetCurrentApartmentType 函数检索的单元在其中执行调用方的类型。"
ms.date: 11/06/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: reference
api_name: GetCurrentApartmentType
api_location: WMINet_Utils.dll
api_type: DLLExport
f1_keywords: GetCurrentApartmentType
helpviewer_keywords: GetCurrentApartmentType function [.NET WMI and performance counters]
topic_type: Reference
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: b250913b55ba59261a666760cc15466b6f9d096e
ms.sourcegitcommit: a53799f81351ad9afb3007cd68846ce6aeeb10cb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/15/2017
---
# <a name="getcurrentapartmenttype-function"></a>GetCurrentApartmentType 函数
检索在其中执行调用方的单元的类型。   
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a>语法  
  
```  
HRESULT GetCurrentApartmentType (
   [in] int                   vFunc, 
   [in] IComThreadingInfo*    ptr, 
   [out] APTTYPE*             aptType
); 
```  

## <a name="parameters"></a>参数

`vFunc`  
[in]未使用此参数。

`ptr`  
[in]指向的指针[IComThreadingInfo](https://msdn.microsoft.com/library/windows/desktop/ms694502(v=vs.85).aspx)实例。

`aptType`  
[out]指向的指针[APTTYPE](https://msdn.microsoft.com/library/windows/desktop/ms693793(v=vs.85).aspx)枚举值，该值指示调用方的单元。

## <a name="return-value"></a>返回值


|返回的常量  |值  |描述  |
|---------|---------|---------|
| `S_OK` | 0 | 已成功完成该函数。 |
| `E_FAIL` | 0x80000008 | 在单元中未执行调用方。 |
  
## <a name="remarks"></a>备注

此函数包装对的调用[IComThreadingInfo::GetCurrentApartmentType](https://msdn.microsoft.com/library/windows/desktop/ms683752(v=vs.85).aspx)方法。

## <a name="requirements"></a>要求  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** WMINet_Utils.idl  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>请参阅  
[WMI 和性能计数器 （非托管 API 参考）](index.md)
