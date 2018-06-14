---
title: SpawnDerivedClass 函数 （非托管 API 参考）
description: SpawnDerivedClass 函数将创建一个派生自对象的新对象。
ms.date: 11/06/2017
api_name:
- SpawnDerivedClass
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- SpawnDerivedClass
helpviewer_keywords:
- SpawnDerivedClass function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: fe93b7ee28db8151345871b0dd716d41227ed565
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33462294"
---
# <a name="spawnderivedclass-function"></a>SpawnDerivedClass 函数
从指定的对象创建新派生的类对象。    
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a>语法  
  
```  
HRESULT SpawnDerivedClass (
   [in] int                  vFunc, 
   [in] IWbemClassObject*    ptr, 
   [in] LONG                 lFlags,
   [out] IWbemClassObject**  ppNewClass); 
```  

## <a name="parameters"></a>参数

`vFunc`  
[in]未使用此参数。

`ptr`  
[in]指向的指针[IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx)实例。

`lFlags`  
[in]保留。 此参数必须为 0。

`ppNewClass`  
[out]接收到新的类定义对象的指针。 如果发生错误，新的对象不是返回，和`ppNewClass`左未修改形式。 其值不能为`null`。

## <a name="return-value"></a>返回值

此函数返回以下值中定义*WbemCli.h*标头文件，或者你可以定义它们常量作为在代码中：

|返回的常量  |值  |描述  |
|---------|---------|---------|
| `WBEM_E_FAILED` | 0x80041001 | 发生了常规错误。 |
| `WBEM_E_INVALID_OPERATION` | 0x80041016 | 已请求了无效的操作，例如从实例中，生成一个类。 |
| `WBEM_E_INCOMPLETE_CLASS` | 源类是未完全定义的或注册 Windows 管理中，因此不允许新的派生的类。 |
| `WBEM_E_OUT_OF_MEMORY` | 0x80041006 | 没有足够的内存是可用于完成该操作。 |
| `WBEM_E_INVALID_PARAMETER` | 0x80041008 | `ppNewClass` 为 `null`。 |
| `WBEM_S_NO_ERROR` | 0 | 函数调用成功。  |
  
## <a name="remarks"></a>备注

此函数包装对的调用[IWbemClassObject::SpawnDerivedClass](https://msdn.microsoft.com/library/aa391436(v=vs.85).aspx)方法。

`ptr` 必须是对象的一个将成为生成的父类的类定义。 返回的对象将成为当前对象的一个子类。

新的对象中返回`ppNewClass`自动成为当前对象的一个子类。 不能重写此行为。 不没有可以用来创建子类 （派生类） 的任何其他方法。

## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** WMINet_Utils.idl  
  
 **.NET framework 版本：** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>请参阅  
[WMI 和性能计数器 （非托管 API 参考）](index.md)
