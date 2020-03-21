---
title: 克隆EnumWbem类对象函数（非托管 API 引用）
description: CloneEnumWbemClassObject 函数创建枚举器的逻辑副本。
ms.date: 11/06/2017
api_name:
- CloneEnumWbemClassObject
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- CloneEnumWbemClassObject
helpviewer_keywords:
- CloneEnumWbemClassObject function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: f2a3a7e848108e50c04f0ec70cf42586755a0a88
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175013"
---
# <a name="cloneenumwbemclassobject-function"></a>CloneEnumWbemClassObject 函数
制作枚举器的逻辑副本，并保留其在枚举中的当前位置。

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a>语法

```cpp
HRESULT CloneEnumWbemClassObject (
   [out] IEnumWbemClassObject**  ppEnum,
   [in] DWORD                    authLevel,
   [in] DWORD                    impLevel,
   [in] IEnumWbemClassObject*    pCurrentEnumWbemClassObject,
   [in] BSTR                     strUser,
   [in] BSTR                     strPassword,
   [in BSTR]                     strAuthority
);
```

## <a name="parameters"></a>parameters

`ppEnum`\
[出]接收指向新[IEnumWbem ClassObject 的指针](/windows/desktop/api/wbemcli/nn-wbemcli-ienumwbemclassobject)。

`authLevel`\
[在]授权级别。

`impLevel`\
[在]模拟级别。

`pCurrentEnumWbemClassObject`\
[出]指向要克隆的[IEnumWbemClassObject 实例](/windows/desktop/api/wbemcli/nn-wbemcli-ienumwbemclassobject)的指针。

`strUser`\
[在]用户名。 有关详细信息，请参阅[ConnectServerWmi](connectserverwmi.md)函数。

`strPassword`\
[在]密码。 有关详细信息，请参阅[ConnectServerWmi](connectserverwmi.md)函数。

`strAuthority`\
[在]用户的域名。 有关详细信息，请参阅[ConnectServerWmi](connectserverwmi.md)函数。

## <a name="return-value"></a>返回值

此函数返回的以下值在*WbemCli.h*标头文件中定义，或者您可以在代码中将它们定义为常量：

|一直  |值  |说明  |
|---------|---------|---------|
| `WBEM_E_FAILED` | 0x80041001 | 出现了一个普遍的失败。 |
| `WBEM_E_INVALID_PARAMETER` | 0x80041008 | 参数无效。 |
| `WBEM_E_OUT_OF_MEMORY` | 0x80041006 | 没有足够的内存可用于完成操作。 |
| `WBEM_E_TRANSPORT_FAILURE` | 0 x80041015 | 当前进程和 WMI 之间的远程过程调用 （RPC） 链路已失败。 |
| `WBEM_S_NO_ERROR` | 0 | 函数调用成功。  |

## <a name="remarks"></a>备注

此函数包装对[IEnumWbem ClassObject：：clone](/windows/desktop/api/wbemcli/nf-wbemcli-ienumwbemclassobject-clone)方法的调用。

此方法仅进行"尽力"复制。 由于许多 CIM 对象的动态性质，新的枚举器可能不会枚举与源枚举器相同的对象集。

如果函数调用失败，您可以通过调用[GetErrorInfo](geterrorinfo.md)函数获取其他错误信息。

## <a name="example"></a>示例

例如，请参阅[IEnumWbem 类对象：：克隆](/windows/desktop/api/wbemcli/nf-wbemcli-ienumwbemclassobject-clone)方法。

## <a name="requirements"></a>要求
 **平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。

 **标题：** WMINet_Utils.idl

 **.NET 框架版本：**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]

## <a name="see-also"></a>另请参阅

- [WMI 和性能计数器（非托管 API 参考）](index.md)
