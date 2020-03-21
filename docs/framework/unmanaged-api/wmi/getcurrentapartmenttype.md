---
title: 获取当前公寓类型函数（非托管 API 参考）
description: GetCurrent公寓类型函数检索调用方正在其中执行的公寓类型。
ms.date: 11/06/2017
api_name:
- GetCurrentApartmentType
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- GetCurrentApartmentType
helpviewer_keywords:
- GetCurrentApartmentType function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: 3fc88f7997ee5a6c25359243e1ee97a041050eb7
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176820"
---
# <a name="getcurrentapartmenttype-function"></a>GetCurrentApartmentType 函数
检索调用方执行操作所在的单元类型。
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT GetCurrentApartmentType (
   [in] int                   vFunc,
   [in] IComThreadingInfo*    ptr,
   [out] APTTYPE*             aptType
);
```  

## <a name="parameters"></a>parameters

`vFunc`  
[在]此参数未使用。

`ptr`  
[在]指向[IComThreadingInfo](/windows/desktop/api/objidlbase/nn-objidlbase-icomthreadinginfo)实例的指针。

`aptType`  
[出]指向[APTTYPE](/windows/win32/api/objidlbase/ne-objidlbase-apttype)枚举值的指针，指示调用方的公寓。

## <a name="return-value"></a>返回值

|一直  |值  |说明  |
|---------|---------|---------|
| `S_OK` | 0 | 功能已成功完成。 |
| `E_FAIL` | 0x80000008 | 调用方未在公寓中执行。 |
  
## <a name="remarks"></a>备注

此函数将调用包起来到[IComThreadingInfo：：获取当前公寓类型](/windows/desktop/api/objidlbase/nf-objidlbase-icomthreadinginfo-getcurrentapartmenttype)方法。

## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。  
  
 **标题：** WMINet_Utils.idl  
  
 **.NET 框架版本：**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>另请参阅

- [WMI 和性能计数器（非托管 API 参考）](index.md)
