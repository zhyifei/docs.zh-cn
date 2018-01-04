---
title: "GetErrorInfo 函数 （非托管 API 参考）"
description: "GetErrorInfo 函数从上一个函数调用中检索错误信息。"
ms.date: 11/06/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: reference
api_name: GetErrorInfo
api_location: WMINet_Utils.dll
api_type: DLLExport
f1_keywords: GetErrorInfo
helpviewer_keywords: GetErrorInfo function [.NET WMI and performance counters]
topic_type: Reference
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: d4b4acde080c61fbfd5cec319c1986b8c86352c4
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="geterrorinfo-function"></a>GetErrorInfo 函数
从以前的函数调用中检索错误信息。  
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a>语法  
  
```  
IErrorInfo* GetErrorInfo(); 
```  

## <a name="return-value"></a>返回值

指向[IErrorInfo](https://msdn.microsoft.com/library/windows/desktop/ms221233(v=vs.85).aspx)对象，如果函数调用成功，或`null`如果失败。
  
## <a name="remarks"></a>备注

此函数包装对的调用[IComThreadingInfo::GetErrorInfo](https://msdn.microsoft.com/library/windows/desktop/ms683752(v=vs.85).aspx)方法。

## <a name="requirements"></a>惠?  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** WMINet_Utils.def  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>请参阅  
[WMI 和性能计数器 （非托管 API 参考）](index.md)
