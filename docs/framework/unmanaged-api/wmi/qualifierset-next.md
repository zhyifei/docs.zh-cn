---
title: QualifierSet_Next 函数 （非托管 API 参考）
description: QualifierSet_Next 函数将检索枚举中的下一步限定符。
ms.date: 11/06/2017
api_name:
- QualifierSet_Next
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- QualifierSet_Next
helpviewer_keywords:
- QualifierSet_Next function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a8232691c697c51b5a480a68c6d952f294a63460
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33460222"
---
# <a name="qualifiersetnext-function"></a>QualifierSet_Next 函数
检索一个枚举，通过调用启动中的下一步限定符[QualifierSet_BeginEnumeration](qualifierset-beginenumeration.md)函数。   

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a>语法  
  
```  
HRESULT QualifierSet_Next (
   [in] int                  vFunc, 
   [in] IWbemQualifierSet*   ptr, 
   [in] LONG                 lFlags,
   [out] BSTR*               pstrName,        
   [out] VARIANT*            pVal,
   [out] LONG*               plFlavor                 
); 
```  

## <a name="parameters"></a>参数

`vFunc`   
[in]未使用此参数。

`ptr`   
[in]指向的指针[IWbemQualifierSet](https://msdn.microsoft.com/library/aa391860(v=vs.85).aspx)实例。

`lFlags`   
[in]保留。 此参数必须为 0。

`pstrName`   
[out]限定符的名称。 如果`null`，此参数是忽略; 否则为`pstrName`应不指向有效`BSTR`或则会发生内存泄漏。 如果不为 null，函数始终会分配一个新`BSTR`时，它返回`WBEM_S_NO_ERROR`。

`pVal`   
[out]成功后，限定符的值。 如果函数失败，`VARIANT`指向`pVal`则不会修改。 如果此参数为`null`，则将忽略参数。

`plFlavor`   
[out]指向接收限定符特色信息长时间的指针。 如果不想风格信息，此参数可以为`null`。 

## <a name="return-value"></a>返回值

此函数返回以下值中定义*WbemCli.h*标头文件，或者你可以定义它们常量作为在代码中：

|返回的常量  |值  |描述  |
|---------|---------|---------|
|`WBEM_E_INVALID_PARAMETER` | 0x80041008 | 参数不是有效的。 |
|`WBEM_E_UNEXPECTED` | 0x8004101d | 调用方未调用[QualifierSet_BeginEnumeration](qualifierset-beginenumeration.md)。 |
|`WBEM_E_OUT_OF_MEMORY` | 0x80041006 | 没有足够的内存，可开始新的枚举。 |
| `WBEM_S_NO_MORE_DATA` | 0x40005 | 没有更多的限定符会保留在枚举中。 |
|`WBEM_S_NO_ERROR` | 0 | 函数调用成功。  |
  
## <a name="remarks"></a>备注

此函数包装对的调用[IWbemQualifierSet::Next](https://msdn.microsoft.com/library/aa391870(v=vs.85).aspx)方法。

你调用`QualifierSet_Next`函数重复直到函数返回枚举所有的限定符`WBEM_S_NO_MORE_DATA`。 若要终止枚举尽早，调用[QualifierSet_EndEnumeration](qualifierset-endenumeration.md)函数。

在枚举过程中返回的限定符的顺序是不确定的。

## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** WMINet_Utils.idl  
  
 **.NET framework 版本：** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>请参阅  
[WMI 和性能计数器 （非托管 API 参考）](index.md)
