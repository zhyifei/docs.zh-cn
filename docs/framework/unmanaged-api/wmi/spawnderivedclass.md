---
title: 生成派生类函数（非托管 API 引用）
description: Spawn 派生类函数创建一个从对象派生的新对象。
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
ms.openlocfilehash: e9784f8a024c788823dc702794b2b86eea1827bb
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79174844"
---
# <a name="spawnderivedclass-function"></a>SpawnDerivedClass 函数
从指定对象创建新派生的类对象。
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT SpawnDerivedClass (
   [in] int                  vFunc,
   [in] IWbemClassObject*    ptr,
   [in] LONG                 lFlags,
   [out] IWbemClassObject**  ppNewClass);
```  

## <a name="parameters"></a>parameters

`vFunc`  
[在]此参数未使用。

`ptr`  
[在]指向[IWbem ClassObject 实例](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject)的指针。

`lFlags`  
[in] 保留。 此参数必须为 0。

`ppNewClass`  
[出]接收指向新类定义对象的指针。 如果发生错误，则不会返回新对象，并且`ppNewClass`未修改。 其值不能为`null`。

## <a name="return-value"></a>返回值

此函数返回的以下值在*WbemCli.h*标头文件中定义，或者您可以在代码中将它们定义为常量：

|一直  |值  |说明  |
|---------|---------|---------|
| `WBEM_E_FAILED` | 0x80041001 | 出现了一个普遍的失败。 |
| `WBEM_E_INVALID_OPERATION` | 0 x80041016 | 请求无效操作，例如从实例生成类。 |
| `WBEM_E_INCOMPLETE_CLASS` | 源类未完全定义或注册到 Windows 管理，因此不允许使用新的派生类。 |
| `WBEM_E_OUT_OF_MEMORY` | 0x80041006 | 没有足够的可用内存来完成该操作。 |
| `WBEM_E_INVALID_PARAMETER` | 0x80041008 | `ppNewClass` 为 `null`。 |
| `WBEM_S_NO_ERROR` | 0 | 函数调用成功。  |
  
## <a name="remarks"></a>备注

此函数将调用包起来到[IWbem ClassObject：：spawn派生类](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-clone)方法。

`ptr`必须是成为生成对象的父类的类定义。 返回的对象将成为当前对象的子类。

返回`ppNewClass`的新对象将自动成为当前对象的子类。 无法重写此行为。 没有其他方法可以创建子类（派生类）。

## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。  
  
 **标题：** WMINet_Utils.idl  
  
 **.NET 框架版本：**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>另请参阅

- [WMI 和性能计数器（非托管 API 参考）](index.md)
