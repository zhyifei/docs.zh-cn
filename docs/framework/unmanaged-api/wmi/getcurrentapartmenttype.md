---
title: GetCurrentApartmentType 函数（非托管 API 参考）
description: GetCurrentApartmentType 函数检索要在其中执行调用方的单元的类型。
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
ms.openlocfilehash: 6ecd2b49d6850a8fae25ddca54f855fdda2ccabb
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73120352"
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

## <a name="parameters"></a>参数

`vFunc`  
中此参数未使用。

`ptr`  
中指向[IComThreadingInfo](/windows/desktop/api/objidlbase/nn-objidlbase-icomthreadinginfo)实例的指针。

`aptType`  
弄指向[APTTYPE](/windows/win32/api/objidlbase/ne-objidlbase-apttype)枚举值的指针，该枚举值指示调用方的单元。

## <a name="return-value"></a>返回值

|返回的常量  |“值”  |描述  |
|---------|---------|---------|
| `S_OK` | 0 | 函数已成功完成。 |
| `E_FAIL` | 0x80000008 | 调用方不在单元中执行。 |
  
## <a name="remarks"></a>备注

此函数包装对[IComThreadingInfo：： GetCurrentApartmentType](/windows/desktop/api/objidlbase/nf-objidlbase-icomthreadinginfo-getcurrentapartmenttype)方法的调用。

## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。  
  
 **标头：** WMINet_Utils .idl  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>请参阅

- [WMI 和性能计数器（非托管 API 参考）](index.md)
