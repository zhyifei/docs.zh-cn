---
title: GetPropertyHandle 函数 （非托管 API 参考）
description: GetPropertyHandle 函数返回一个唯一的句柄的 identies 属性。
ms.date: 11/06/2017
api_name:
- GetPropertyHandle
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- GetPropertyHandle
helpviewer_keywords:
- GetPropertyHandle function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 94171b0708c97eb7510e916e451ed03645d706f3
ms.sourcegitcommit: 3ab9254890a52a50762995fa6d7d77a00348db7e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2018
ms.locfileid: "46471114"
---
# <a name="getpropertyhandle-function"></a>GetPropertyHandle 函数
返回标识属性的唯一句柄。

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a>语法  
  
```  
HRESULT GetPropertyHandle (
   [in] int                  vFunc, 
   [in] IWbemObjectAccess*   ptr, 
   [in] LPCWSTR              wszPropertyName,
   [out] CIMTYPE*            pType,
   [out] long*               pHandle
); 
```  

## <a name="parameters"></a>参数

`vFunc`  
[in]此参数是未使用。

`ptr`  
[in]一个指向[IWbemObjectAccess](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemobjectaccess)实例。

`wszPropertyName`  
[in]一个以 null 结尾的 UTF16 编码 characaters 包含属性名称的字符串。   

`pType`  
[out]一个指向[ `CIMTYPE` ](https://msdn.microsoft.com/library/aa386309(v=vs.85).aspx)表示属性的 CIM 类型的枚举成员。

`pHandle`   
[out]指向一个整数，包含属性句柄的指针。

## <a name="return-value"></a>返回值

此函数返回以下值中定义*WbemCli.h*标头文件，也可以在定义它们为常量在代码中：

|返回的常量  |“值”  |描述  |
|---------|---------|---------|
|`WBEM_E_NOT_FOUND` | 0x80041002 | 找不到指定的属性名称。 |
|`WBEM_E_INVALID_PARAMETER` | 0x80041008 | 参数不是有效的。 |
|`WBEM_E_NOT_SUPPORTED` | 0x8004100c | 请求的属性属于类型是`CIM_OBJECT`或`CIM_ARRAY`。 |
|`WBEM_S_NO_ERROR` | 0 | 函数调用成功。  |
  
## <a name="remarks"></a>备注

此函数包装对的调用[IWbemClassObject::GetPropertyHandle](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemobjectaccess-getpropertyhandle)方法。

可以使用此句柄来标识属性，使用时[IWbemObjectAccess](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemobjectaccess)方法来读取或写入属性值。

句柄可以检索所有数据类型的属性以外`CIM_OBJECT`和`CIM_ARRAY`。 返回一个类的所有实例句柄的工作。

## <a name="requirements"></a>要求  
**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** WMINet_Utils.idl  
  
 **.NET Framework 版本：**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>请参阅  
[WMI 和性能计数器 （非托管 API 参考）](index.md)
