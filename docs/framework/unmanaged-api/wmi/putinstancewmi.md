---
title: PutInstanceWmi 函数（非托管 API 参考）
description: PutInstanceWmi 函数创建或更新现有类的实例。
ms.date: 11/06/2017
api_name:
- PutInstanceWmi
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- PutInstanceWmi
helpviewer_keywords:
- PutInstanceWmi function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 37810ecab2e02d4ec250dd2a4b2657c3b898f714
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2019
ms.locfileid: "70798371"
---
# <a name="putinstancewmi-function"></a>PutInstanceWmi 函数

创建或更新现有类的实例。 将该实例写入 WMI 存储库。

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a>语法

```cpp
HRESULT PutInstanceWmi (
   [in] IWbemClassObject*    pInst,
   [in] long                 lFlags,
   [in] IWbemContext*        pCtx,
   [out] IWbemCallResult**   ppCallResult
);
```

## <a name="parameters"></a>参数

`pInst`\
中指向要写入的实例的指针。

`lFlags`\
中影响此函数的行为的标志的组合。 以下值是在*WbemCli*头文件中定义的，也可以在代码中将它们定义为常量：

|返回的常量  |值  |描述  |
|---------|---------|---------|
| `WBEM_FLAG_USE_AMENDED_QUALIFIERS` | 0x20000 | 如果已设置，WMI 不会将任何限定符存储在**修改**后的风格。 <br> 如果未设置，则假定此对象未本地化，且所有限定符都与此实例一起存储。 |
| `WBEM_FLAG_CREATE_OR_UPDATE` | 0 | 如果实例不存在，请创建它，如果已存在，则覆盖它。 |
| `WBEM_FLAG_UPDATE_ONLY` | 1 | 更新实例。 此实例必须存在，调用才能成功。 |
| `WBEM_FLAG_CREATE_ONLY` | 2 | 创建实例。 如果该实例已存在，则调用失败。 |
| `WBEM_FLAG_RETURN_IMMEDIATELY` | 0x10 | 标志导致半同步调用。 |

`pCtx`\
中通常，此值为`null`。 否则，它是指向提供请求的类的提供程序可以使用的[IWbemContext](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemcontext)实例的指针。

`ppCallResult`\
弄如果`null`为，则不使用此参数。 如果`lFlags`包含`WBEM_FLAG_RETURN_IMMEDIATELY` ，`WBEM_S_NO_ERROR`则函数立即返回。 `ppCallResult` 参数接收指向新 [IWbemCallResult](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemcallresult) 对象的指针。

## <a name="return-value"></a>返回值

此函数返回的以下值是在*WbemCli*头文件中定义的，也可以在代码中将它们定义为常量：

|返回的常量  |值  |描述  |
|---------|---------|---------|
| `WBEM_E_ACCESS_DENIED` | 0x80041003 | 用户没有更新指定类的实例的权限。 |
| `WBEM_E_FAILED` | 0x80041001 | 发生了未指定的错误。 |
| `WBEM_E_INVALID_CLASS` | 0x80041010 | 支持此实例的类无效。 |
| `WBEM_E_ILLEGAL_NULL` | 0x80041028 | 为`null`不能是`null`的属性指定了，例如，使用**索引**或**Not_Null**限定符标记的属性。 |
| `WBEM_E_INVALID_OBJECT` | 0x8004100f | 指定的实例无效。 （例如，使用类`PutInstanceWmi`调用会返回此值。） |
| `WBEM_E_INVALID_PARAMETER` | 0x80041008 | 参数无效。 |
| `WBEM_E_ALREADY_EXISTS` | 0x80041019 | 已`WBEM_FLAG_CREATE_ONLY`指定标志，但该实例已存在。 |
| `WBEM_E_NOT_FOUND` | 0x80041002 | `WBEM_FLAG_UPDATE_ONLY`已在中`lFlags`指定，但该实例不存在。 |
| `WBEM_E_OUT_OF_MEMORY` | 0x80041006 | 没有足够的内存可用来完成此操作。 |
| `WBEM_E_SHUTTING_DOWN` | 0x80041033 | WMI 可能已停止并重新启动。 再次调用[ConnectServerWmi](connectserverwmi.md) 。 |
| `WBEM_E_TRANSPORT_FAILURE` | 0x80041015 | 当前进程与 WMI 之间的远程过程调用（RPC）链接失败。 |
| `WBEM_S_NO_ERROR` | 0 | 函数调用成功。 |

## <a name="remarks"></a>备注

此函数包装对[IWbemServices：:P utinstance](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemservices-putinstance)方法的调用。

`PutInstanceWmi`函数仅支持创建实例和更新现有类的实例。  根据`pCtx`参数的设置方式，将更新实例的部分或全部属性。

当指向`pInst`的实例属于子类时，Windows Management 会调用所有负责派生子类的类的提供程序。 所有这些提供程序必须成功，原始`PutInstanceWmi`请求才能成功。 首先调用支持层次结构中最顶层的类的提供程序。 调用顺序继续使用最顶层类的子类，并从上到下继续，直到 Windows 管理到达所属`pInst`的类的提供程序。
Windows 管理不会为实例的任何子类调用提供程序。

当应用程序必须更新属于类层次结构的实例时，该`pInst`参数必须指向包含要修改的属性的实例。 也就是说，假设有一个属于**ClassB**的目标实例。 **ClassB**实例派生自**ClassA**， **ClassA**定义属性**PropA**。 如果应用程序要对**ClassB**实例中的`pInst` **PropA**值进行更改，则必须将其设置为该实例而不是**ClassA**的实例。

不`PutInstanceWmi`允许在抽象类的实例上调用。

如果函数调用失败，可以通过调用[GetErrorInfo](geterrorinfo.md)函数获取其他错误信息。

## <a name="requirements"></a>要求

**适用**请参阅[系统需求](../../get-started/system-requirements.md)。

**标头：** WMINet_Utils.idl

**.NET Framework 版本：** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]

## <a name="see-also"></a>请参阅

- [WMI 和性能计数器（非托管 API 参考）](index.md)
