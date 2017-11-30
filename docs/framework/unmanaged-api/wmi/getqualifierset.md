---
title: "GetQualifierSet 函数 （非托管 API 参考）"
description: "GetQualifierSet 函数可检索为类或实例设置的限定符。"
ms.date: 11/06/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: reference
api_name: GetQualifierSet
api_location: WMINet_Utils.dll
api_type: DLLExport
f1_keywords: GetQualifierSet
helpviewer_keywords: GetQualifierSet function [.NET WMI and performance counters]
topic_type: Reference
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 15d384003f3a18124a07d83a8308f4b8a5c6a31b
ms.sourcegitcommit: a53799f81351ad9afb3007cd68846ce6aeeb10cb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/15/2017
---
# <a name="getqualifierset-function"></a>GetQualifierSet 函数
检索为的类实例或类定义设置的限定符。

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a>语法  
  
```  
HRESULT GetQualifierSet (
   [in] int                 vFunc, 
   [in] IWbemClassObject*   ptr, 
   [out] IWbemQualifierSet  **ppQualSet
); 
```  

## <a name="parameters"></a>参数

`vFunc`  
[in]未使用此参数。

`ptr`  
[in]指向的指针[IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx)实例。

`ppQualSet`  
[out]接收的接口指针，它允许访问的类对象的限定符。 `ppQualSet` 不能为 `null`。 如果发生错误，则不返回一个新对象，并且指针仍未修改。 

## <a name="return-value"></a>返回值

此函数返回以下值中定义*WbemCli.h*标头文件，或者你可以定义它们常量作为在代码中：

|返回的常量  |值  |描述  |
|---------|---------|---------|
|`WBEM_E_FAILED` | 0x80041001 | 发生了常规错误。 |
|`WBEM_E_NOT_FOUND` | 0x80041002 | 指定的方法不存在。 |
|`WBEM_E_OUT_OF_MEMORY` | 0x80041006 | 没有足够的内存是可用于完成该操作。 |
|`WBEM_E_INVALID_PARAMETER` | 0x80041008 | 参数是`null`。 |
|`WBEM_S_NO_ERROR` | 0 | 函数调用成功。  |
  
## <a name="remarks"></a>备注

此函数包装对的调用[IWbemClassObject::GetQualifierSet](https://msdn.microsoft.com/library/aa391451(v=vs.85).aspx)方法。 

[IWbemQualifierSet 指针](https://msdn.microsoft.com/library/aa391860(v=vs.85).aspx)允许调用方添加、 编辑或删除这些限定符。 此类添加、 编辑或删除的限定符应用于整个的实例或类定义。

## <a name="requirements"></a>要求  
**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** WMINet_Utils.idl  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>请参阅  
[WMI 和性能计数器 （非托管 API 参考）](index.md)
