---
title: 获取方法源函数（非托管 API 引用）
description: GetMethodOrigin 函数确定声明方法的类。
ms.date: 11/06/2017
api_name:
- GetMethodOrigin
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- GetMethodOrigin
helpviewer_keywords:
- GetMethodOrigin function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: 5b4609b6649be875aea7dfcf52ba36b1e98ab7bc
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176794"
---
# <a name="getmethodorigin-function"></a>GetMethodOrigin 函数
确定声明方法的类。

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a>语法  
  
```cpp  
HRESULT GetMethodOrigin (
   [in] int                 vFunc,
   [in] IWbemClassObject*   ptr,
   [in] LPCWSTR             wszMethodName,
   [out] BSTR*              pstrClassName
);
```  

## <a name="parameters"></a>parameters

`vFunc`  
[在]此参数未使用。

`ptr`  
[在]指向[IWbem ClassObject 实例](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject)的指针。

`wszMethodName`  
[在]正在请求其拥有类的对象的方法的名称。

`pstrClassName`  
[出]接收拥有 方法的类的名称。

## <a name="return-value"></a>返回值

此函数返回的以下值在*WbemCli.h*标头文件中定义，或者您可以在代码中将它们定义为常量：

|一直  |值  |说明  |
|---------|---------|---------|
|`WBEM_E_NOT_FOUND` | 0 x80041002 | 找不到指定的方法。 |
|`WBEM_E_INVALID_PARAMETER` | 0x80041008 | 一个或多个参数无效。 |
|`WBEM_S_NO_ERROR` | 0 | 函数调用成功。  |
  
## <a name="remarks"></a>备注

此函数包装对[IWbem ClassObject 的调用：：获取方法原点](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getmethod)方法。

由于类可以从一个或多个基类继承方法，因此开发人员通常希望确定在其中定义给定方法的类。

在`pstrClassName`调用函数之前，参数不能指向`BSTR`有效，因为这是一个`out`参数;因此，参数在调用函数之前，不能指向该参数。函数返回后，此指针不会处理。

## <a name="requirements"></a>要求  
**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。  
  
 **标题：** WMINet_Utils.idl  
  
 **.NET 框架版本：**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>另请参阅

- [WMI 和性能计数器（非托管 API 参考）](index.md)
