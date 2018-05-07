---
title: FormatFromRawValue 函数 （非托管 API 参考）
description: FormatFromRawValue 函数将转换为指定的格式的原始性能数据。
ms.date: 11/21/2017
api_name:
- FormatFromRawValue
api_location:
- PerfCounter.dll
api_type:
- DLLExport
f1_keywords:
- FormatFromRawValue
helpviewer_keywords:
- FormatFromRawValue function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e0710b26237b350f1dfbc7d2464b7a131373604e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="formatfromrawvalue-function"></a>FormatFromRawValue 函数
基于时间的格式转换是否将转换为指定的格式中，一个原始性能数据值或两个原始性能数据值。   
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a>语法  
  
```  
int FormatFromRawValue (
   [in] uint                    dwCounterType, 
   [in] uint                    dwFormat, 
   [in] long*                   pTimeBase,
   [in] PDH_RAW_COUNTER*        pRawValue1,
   [in] PDH_RAW_COUNTER*        pRawValue2,
   [out] PDH_FMT_COUNTERVALUE*  pFmtValue
); 
```  

## <a name="parameters"></a>参数

`dwCounterType`  
[in]计数器类型中。 计数器类型的列表，请参阅[WMI 性能计数器类型](https://msdn.microsoft.com/library/aa394569(v=vs.85).aspx)。 `dwCounterType` 可以是除任何计数器类型`PERF_LARGE_RAW_FRACTION`和`PERF_LARGE_RAW_BASE`。 

`dwFormat`  
[in]要转换的原始性能数据为格式。 它可以是以下值之一：

|返回的常量  |值  |描述 |
|---------|---------|---------|
| `PDH_FMT_DOUBLE` |0x00000200 | 以双精度浮点值的形式返回计算的值。 | 
| `PDH_FMT_LARGE` | 0x00000400 | 以 64 位整数的形式返回计算的值。 |
| `PDH_FMT_LONG` | 0x00000100 | 返回计算的值为 32 位整数。 |

其中一个以前的值可以是以下缩放标志的其中一条 or 运算：

|返回的常量  |值  |描述 |
|---------|---------|---------|
| `PDH_FMT_NOSCALE` | 0x00001000 | 不适用于该计数器的比例因子。 |
| `PDH_FMT_1000` | 0x00002000 | 最终值乘以 1000。 | 

`pTimeBase`  
[in]指向时间基准，如有必要进行格式转换的指针。 如果时间基准信息不是必需的格式转换，则忽略此参数的值。

`pRawValue1` [in]指向的指针[ `PDH_RAW_COUNTER` ](https://msdn.microsoft.com/library/windows/desktop/aa373060(v=vs.85).aspx)结构，它表示原始性能值。

`pRawValue2` [in]指向的指针[ `PDH_RAW_COUNTER` ](https://msdn.microsoft.com/library/windows/desktop/aa373060(v=vs.85).aspx)结构，它表示第二个原始性能值。 如果第二个的原始性能值不是必需的此参数应为`null`。

`pFmtValue` [out]指向的指针[ `PDH_FMT_COUNTERVALUE` ](https://msdn.microsoft.com/library/windows/desktop/aa373050(v=vs.85).aspx)接收格式化的性能值的结构。

## <a name="return-value"></a>返回值

此函数返回以下值：

|返回的常量  |值  |描述  |
|---------|---------|---------|
| `ERROR_SUCCESS` | 0 | 函数调用是成功的。 |
| `PDH_INVALID_ARGUMENT` | 0xC0000BBD | 一个必需的参数已丢失或不正确。 | 
| `PDH_INVALID_HANDLE` | 0xC0000BBC | 句柄不是有效的 PDH 对象。 |
  
## <a name="remarks"></a>备注

此函数包装对的调用[FormatFromRawValue](https://msdn.microsoft.com/library/ms231047(v=vs.85).aspx)函数。

## <a name="requirements"></a>要求  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **库：** PerfCounter.dll  
  
 **.NET framework 版本：** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>请参阅  
[WMI 和性能计数器 （非托管 API 参考）](index.md)
