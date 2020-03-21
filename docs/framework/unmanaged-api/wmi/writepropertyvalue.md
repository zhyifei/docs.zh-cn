---
title: 写入属性值函数（非托管 API 引用）
description: WritePropertyValue 函数将字节写入属性。
ms.date: 11/06/2017
api_name:
- WritePropertyValue
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- WritePropertyValue
helpviewer_keywords:
- WritePropertyValue function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: 4a950beef2e9bf8c0230d6a38008d75f89373410
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79174831"
---
# <a name="writepropertyvalue-function"></a>WritePropertyValue 函数
将指定数量的字节写入由属性句柄标识的属性。

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a>语法  
  
```cpp  
HRESULT WritePropertyValue (
   [in] int                  vFunc,
   [in] IWbemObjectAccess*   ptr,
   [in] long                 lHandle,
   [in] long                 lNumBytes,
   [in] byte*                aData
);
```  

## <a name="parameters"></a>parameters

`vFunc`  
[在]此参数未使用。

`ptr`  
[在]指向[IWbemObjectAccess](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemobjectaccess)实例的指针。

`lHandle`  
[在]包含标识此属性的句柄的整数。 可以通过调用[GetPropertyHandle](getpropertyhandle.md)函数来检索句柄。

`lNumBytes`  
[在]写入属性的字节数。 有关详细信息，请参阅[备注](#remarks)部分。

`pHandle`[出]指向包含数据的字节数组的指针。

## <a name="return-value"></a>返回值

此函数返回的以下值在*WbemCli.h*标头文件中定义，或者您可以在代码中将它们定义为常量：

|一直  |值  |说明  |
|---------|---------|---------|
|`WBEM_E_INVALID_PARAMETER` | 0x80041008 | 参数无效。 |
|`WBEM_E_TYPE_MISMATCH` | 0x80041005 | 出现类型不匹配。 |
|`WBEM_S_NO_ERROR` | 0 | 函数调用成功。  |
  
## <a name="remarks"></a>备注

此函数将调用包起来到[IWbemClassObject：：WritePropertyValue](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemobjectaccess-writepropertyvalue)方法。

使用此函数可以设置字符串和所有其他非`DWORD`或非`QWORD`数据。

对于非字符串属性值，`lNumBytes`必须为指定的属性类型的正确数据大小。 对于字符串属性值，`lNumBytes`必须为指定字符串的长度（以字节为单位），并且字符串本身的长度（以字节为单位）并且后面必须使用 null 终止字符。

## <a name="requirements"></a>要求  
**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。  
  
 **标题：** WMINet_Utils.idl  
  
 **.NET 框架版本：**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>另请参阅

- [WMI 和性能计数器（非托管 API 参考）](index.md)
