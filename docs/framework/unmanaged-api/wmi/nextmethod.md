---
title: NextMethod 函数 （非托管 API 参考）
description: NextMethod 函数检索枚举中的下一步方法。
ms.date: 11/06/2017
api_name:
- NextMethod
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- NextMethod
helpviewer_keywords:
- NextMethod function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: cd4559663194cb845fb0cc040e1f6739e38caa0e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33461138"
---
# <a name="nextmethod-function"></a>NextMethod 函数
检索到的调用开始枚举中的下一步方法[BeginMethodEnumeration](beginmethodenumeration.md)。  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a>语法  
  
```  
HRESULT NextMethod (
   [in] int                 vFunc, 
   [in] IWbemClassObject*   ptr, 
   [in] LONG                lFlags,
   [out] BSTR*              pName,
   [out] IWbemClassObject** ppInSignature,
   [out] IWbemClassObject** ppOutSignature   
); 
```  

## <a name="parameters"></a>参数

`vFunc`  
[in]未使用此参数。

`ptr`  
[in]指向的指针[IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx)实例。

`lFlags`  
[in]保留。 此参数必须为 0。

`pName`  
[out]一个指针，它指向`null`之前调用。 当函数返回时，新的地址`BSTR`包含方法的名称。 

`ppSignatureIn`  
[out]一个指针，它接收一个指针，到[IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx)包含`in`方法的参数。 

`ppSignatureOut`  
[out]一个指针，它接收一个指针，到[IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx)包含`out`方法的参数。 

## <a name="return-value"></a>返回值

此函数返回以下值中定义*WbemCli.h*标头文件，或者你可以定义它们常量作为在代码中：

|返回的常量  |值  |描述  |
|---------|---------|---------|
| `WBEM_E_UNEXPECTED` | 0x8004101d | 没有不需要调用[ `BeginEnumeration` ](beginenumeration.md)函数。 |
| `WBEM_S_NO_ERROR` | 0 | 函数调用成功。  |
| `WBEM_S_NO_MORE_DATA` | 0x40005 | 枚举中没有更多属性。 |
  
## <a name="remarks"></a>备注

此函数包装对的调用[IWbemClassObject::NextMethod](https://msdn.microsoft.com/library/aa391454(v=vs.85).aspx)方法。

调用方通过调用开始枚举序列[BeginMethodEnumeration](beginmethodenumeration.md)函数，并随后调用 [NextMethod] 函数，直到函数返回`WBEM_S_NO_MORE_DATA`。 调用方 （可选） 通过调用完成序列[EndMethodEnumeration](endmethodenumeration.md)。 调用方可能较早终止枚举，通过调用[EndMethodEnumeration](endmethodenumeration.md)在任何时间。

## <a name="example"></a>示例

有关 c + + 示例，请参阅[IWbemClassObject::NextMethod](https://msdn.microsoft.com/library/aa391454(v=vs.85).aspx)方法。

## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** WMINet_Utils.idl  
  
 **.NET framework 版本：** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>请参阅  
[WMI 和性能计数器 （非托管 API 参考）](index.md)
