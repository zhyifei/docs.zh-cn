---
title: "GetObjectText 函数 （非托管 API 参考）"
description: "GetObjectText 函数返回对象的文本呈现用 MOF 语法。"
ms.date: 11/06/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: reference
api_name: GetObjectText
api_location: WMINet_Utils.dll
api_type: DLLExport
f1_keywords: GetObjectText
helpviewer_keywords: GetObjectText function [.NET WMI and performance counters]
topic_type: Reference
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 0b47dc73bb9da71b0c8593aa5758179327d7572d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="getobjecttext-function"></a>GetObjectText 函数
返回对象的文本呈现中的托管对象格式 (MOF) 语法。

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a>语法  
  
```  
HRESULT GetObjectText (
   [in] int                vFunc, 
   [in] IWbemClassObject*   ptr, 
   [in] LONG                lFlags,
   [out] BSTR*              pstrObjectText
); 
```  

## <a name="parameters"></a>参数

`vFunc`  
[in]未使用此参数。

`ptr`  
[in]指向的指针[IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx)实例。

`lFlags`  
[in]通常 0。 如果`WBEM_FLAG_NO_FLAVORS`（或 0x1） 指定，限定符是包含不带传播或风格的信息。

`pstrObjectText`   
[out]指向的指针`null`条目。 返回时，新分配`BSTR`，该字符串包含对象 MOF 语法呈现。  

## <a name="return-value"></a>返回值

此函数返回以下值中定义*WbemCli.h*标头文件，或者你可以定义它们常量作为在代码中：

|返回的常量  |“值”  |描述  |
|---------|---------|---------|
|`WBEM_E_FAILED` | 0x80041001 | 发生了常规错误。 |
|`WBEM_E_INVALID_PARAMETER` | 0x80041008 | 参数不是有效的。 |
|`WBEM_E_OUT_OF_MEMORY` | 0x80041006 | 没有足够的内存是可用于完成该操作。 |
|`WBEM_S_NO_ERROR` | 0 | 函数调用成功。  |
  
## <a name="remarks"></a>备注

此函数包装对的调用[IWbemClassObject::GetObjectText](https://msdn.microsoft.com/library/aa391448(v=vs.85).aspx)方法。

返回的 MOF 文本不包含所有对象的相关信息，但仅足够 MOF 编译器要能够重新创建原始对象的信息。 例如，错误报告中不包括包含任何传播的限定符或父类属性。

以下算法用于重新构造方法的参数的文本：

1. 参数被 resequenced 按其标识符值的顺序。
1. 指定为参数`[in]`和`[out]`合并为单个参数。
 
`pstrObjectText`必须是指向`null`函数调用时，它必须不指向是之前调用方法有效，因为将会释放指针的字符串。

## <a name="requirements"></a>惠?  
**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** WMINet_Utils.idl  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>请参阅  
[WMI 和性能计数器 （非托管 API 参考）](index.md)
