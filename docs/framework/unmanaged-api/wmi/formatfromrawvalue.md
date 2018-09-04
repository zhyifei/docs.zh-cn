---
title: FormatFromRawValue 函数 （非托管 API 参考）
description: FormatFromRawValue 函数将转换为指定格式的原始性能数据。
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
ms.openlocfilehash: 95ef445d41672c5c2895bd7115afb6a73a57e8f9
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/04/2018
ms.locfileid: "43542162"
---
# <a name="formatfromrawvalue-function"></a>FormatFromRawValue 函数
如果格式转换是基于时间的，则将一个或两个原始性能数据值转换为指定格式。   
  
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
[in]计数器类型。 计数器类型的列表，请参阅[WMI 性能计数器类型](/windows/desktop/WmiSdk/wmi-performance-counter-types)。 `dwCounterType` 可以是任何计数器类型除外`PERF_LARGE_RAW_FRACTION`和`PERF_LARGE_RAW_BASE`。 

`dwFormat`  
[in]若要将原始性能数据转换为的格式。 它可以是下列值之一：

|返回的常量  |“值”  |描述 |
|---------|---------|---------|
| `PDH_FMT_DOUBLE` |0x00000200 | 返回作为双精度浮点值的计算的值。 | 
| `PDH_FMT_LARGE` | 0x00000400 | 以 64 位整数形式返回计算的值。 |
| `PDH_FMT_LONG` | 0x00000100 | 返回作为 32 位整数的计算的值。 |

其中一个以前的值可以是或运算的以下缩放标志之一：

|返回的常量  |“值”  |描述 |
|---------|---------|---------|
| `PDH_FMT_NOSCALE` | 0x00001000 | 不适用于计数器的比例因子。 |
| `PDH_FMT_1000` | 0x00002000 | 最终值乘以 1,000。 | 

`pTimeBase`  
[in]时间基准，如有必要格式转换为指向的指针。 如果没有格式转换所需时间基本信息，则忽略此参数的值。

`pRawValue1` [in]一个指向[ `PDH_RAW_COUNTER` ](https://msdn.microsoft.com/library/windows/desktop/aa373060(v=vs.85).aspx)结构，它表示原始性能值。

`pRawValue2` [in]一个指向[ `PDH_RAW_COUNTER` ](https://msdn.microsoft.com/library/windows/desktop/aa373060(v=vs.85).aspx)结构，它表示第二个原始性能值。 如果第二个原始性能值不是必需的此参数应为`null`。

`pFmtValue` [out]一个指向[ `PDH_FMT_COUNTERVALUE` ](https://msdn.microsoft.com/library/windows/desktop/aa373050(v=vs.85).aspx)接收格式化的性能值的结构。

## <a name="return-value"></a>返回值

此函数返回以下值：

|返回的常量  |“值”  |描述  |
|---------|---------|---------|
| `ERROR_SUCCESS` | 0 | 函数调用是成功的。 |
| `PDH_INVALID_ARGUMENT` | 0xC0000BBD | 必需的参数已丢失或不正确。 | 
| `PDH_INVALID_HANDLE` | 0xC0000BBC | 句柄不是有效的 PDH 对象。 |
  
## <a name="remarks"></a>备注

此函数包装对的调用[FormatFromRawValue](https://msdn.microsoft.com/library/ms231047(v=vs.85).aspx)函数。

## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **库：** PerfCounter.dll  
  
 **.NET Framework 版本：**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>请参阅  
[WMI 和性能计数器 （非托管 API 参考）](index.md)
