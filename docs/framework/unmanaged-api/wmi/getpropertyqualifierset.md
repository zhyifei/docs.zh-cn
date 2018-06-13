---
title: GetPropertyQualifierSet 函数 （非托管 API 参考）
description: GetPropertyQualifierSet 函数可检索为属性设置的限定符。
ms.date: 11/06/2017
api_name:
- GetPropertyQualifierSet
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- GetPropertyQualifierSet
helpviewer_keywords:
- GetPropertyQualifierSet function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d2951733211737f06cd737b20bd1537277be1be1
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33461472"
---
# <a name="getpropertyqualifierset-function"></a>GetPropertyQualifierSet 函数
检索为特定的属性设置的限定符。

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a>语法  
  
```  
HRESULT GetPropertyQualifierSet (
   [in] int                 vFunc, 
   [in] IWbemClassObject*   ptr, 
   [in] LPCWSTR             wszProperty,
   [out] IWbemQualifierSet  **ppQualSet
); 
```  

## <a name="parameters"></a>参数

`vFunc`  
[in]未使用此参数。

`ptr`  
[in]指向的指针[IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx)实例。

`wszMethod`  
[in]属性名称。 `wszProperty` 必须指向有效`LPCWSTR`。 

`ppQualSet`  
[out]接收的接口指针，它允许访问的属性的限定符。 `ppQualSet` 不能为 `null`。 如果出现错误，则不返回一个新对象，并且指针设置为指向`null`。 

## <a name="return-value"></a>返回值

此函数返回以下值中定义*WbemCli.h*标头文件，或者你可以定义它们常量作为在代码中：

|返回的常量  |值  |描述  |
|---------|---------|---------|
|`WBEM_E_FAILED` | 0x80041001 | 发生了常规错误。 |
| `WBEM_E_NOT_FOUND` | 0x80041002 | 指定的方法不存在。 |
|`WBEM_E_OUT_OF_MEMORY` | 0x80041006 | 没有足够的内存是可用于完成该操作。 |
|`WBEM_E_INVALID_PARAMETER` | 0x80041008 | 参数是`null`。 |
| `WBEM_E_SYSTEM_PROPERTY` | 0x80041030 | 该函数尝试获取限定符的系统属性。 |
|`WBEM_S_NO_ERROR` | 0 | 函数调用成功。  |
  
## <a name="remarks"></a>备注

此函数包装对的调用[IWbemClassObject::GetPropertyQualifierSet](https://msdn.microsoft.com/library/aa391450(v=vs.85).aspx)方法。 

仅当当前对象是 CIM 类定义，被支持对此函数的调用。 方法操作不可用于[IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) ponters 指向 CIM 实例。

因为每个方法可能具有其自己的限定符， [IWbemQualifierSet 指针](https://msdn.microsoft.com/library/aa391860(v=vs.85).aspx)允许调用方添加、 编辑或删除这些限定符。

由于系统属性具有不到限定符，该函数将返回`WBEM_E_SYSTEM_PROPERTY`如果你尝试获取[IWbemQualifierSet](https://msdn.microsoft.com/library/aa391860(v=vs.85).aspx)系统属性的指针。

## <a name="requirements"></a>要求  
**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** WMINet_Utils.idl  
  
 **.NET framework 版本：** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>请参阅  
[WMI 和性能计数器 （非托管 API 参考）](index.md)
