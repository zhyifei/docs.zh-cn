---
title: 生成实例函数（非托管 API 引用）
description: SpawnInstance 函数创建类的新实例。
ms.date: 11/06/2017
api_name:
- SpawnInstance
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- SpawnInstance
helpviewer_keywords:
- SpawnInstance function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: a15eb8123c1ee807444bdb4c6fe71cdccc08f434
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176716"
---
# <a name="spawninstance-function"></a>SpawnInstance 函数
创建类的新实例。
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT SpawnInstance (
   [in] int                  vFunc,
   [in] IWbemClassObject*    ptr,
   [in] LONG                 lFlags,
   [out] IWbemClassObject**  ppNewInstance);
```  

## <a name="parameters"></a>parameters

`vFunc`  
[在]此参数未使用。

`ptr`  
[在]指向[IWbem ClassObject 实例](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject)的指针。

`lFlags`  
[in] 保留。 此参数必须为 0。

`ppNewInstance`  
[出]接收指向类新实例的指针。 如果发生错误，则不会返回新对象，并且`ppNewInstance`未修改。

## <a name="return-value"></a>返回值

此函数返回的以下值在*WbemCli.h*标头文件中定义，或者您可以在代码中将它们定义为常量：

|一直  |值  |说明  |
|---------|---------|---------|
| `WBEM_E_INCOMPLETE_CLASS` | 0 x80041020 | `ptr`不是有效的类定义，不能生成新实例。 要么不完整，要么没有通过调用[PutClassWmi](putclasswmi.md)在 Windows 管理中注册。 |
| `WBEM_E_OUT_OF_MEMORY` | 0x80041006 | 没有足够的可用内存来完成该操作。 |
| `WBEM_E_INVALID_PARAMETER` | 0x80041008 | `ppNewClass` 为 `null`。 |
| `WBEM_S_NO_ERROR` | 0 | 函数调用成功。  |
  
## <a name="remarks"></a>备注

此函数将调用包起来到[IWbem ClassObject：：spawnInstance](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-spawninstance)方法。

`ptr`必须是从 Windows 管理获取的类定义。 （请注意，支持从实例生成实例，但返回的实例为空。然后，使用此类定义创建新实例。 如果要将实例写入 Windows 管理，则需要调用[PutInstanceWmi](putinstancewmi.md)函数。

返回`ppNewClass`的新对象将自动成为当前对象的子类。 无法重写此行为。 没有其他方法可以创建子类（派生类）。

## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。  
  
 **标题：** WMINet_Utils.idl  
  
 **.NET 框架版本：**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>另请参阅

- [WMI 和性能计数器（非托管 API 参考）](index.md)
