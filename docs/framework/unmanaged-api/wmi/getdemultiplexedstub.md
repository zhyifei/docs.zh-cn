---
title: "GetDemultiplexedStub 函数 （非托管 API 参考）"
description: "GetDemultiplexedStub 函数将创建的对象转发器接收器，以帮助客户端在从 Windows 管理接收异步调用。"
ms.date: 11/06/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: reference
api_name: GetDemultiplexedStub
api_location: WMINet_Utils.dll
api_type: DLLExport
f1_keywords: GetDemultiplexedStub
helpviewer_keywords: GetDemultiplexedStub function [.NET WMI and performance counters]
topic_type: Reference
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 6ba7ca9941dc148444a4c605fecc8aaf150e8601
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="getdemultiplexedstub-function"></a>GetDemultiplexedStub 函数
创建的对象转发器接收器，以帮助客户端在从 Windows 管理接收异步调用。
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a>语法  
  
```  
HRESULT GetDemultiplexedStub (
   [in] IUnknown*    pObject, 
   [in] boolean      isLocal, 
   [out] IUnknown**  ppObject
); 
```  

## <a name="parameters"></a>参数

`pObject`  
[in]指向客户端的过程中实现的[IWbemObjectSink](https://msdn.microsoft.com/en-us/library/aa391787(v=vs.85).aspx)。

`isLocal`  
[in]一个标志，指示该事件是否本地 (`true`); 否则为`false`。

`ppObject`  
[out]对象的转发器接收器有助于客户端在从 Windows 管理接收异步调用。

## <a name="return-value"></a>返回值

如果函数成功，则返回值是`S_OK`(0)。

如果函数失败，返回值将为非零错误代码。 若要获得扩展的错误信息，调用[GetErrorInfo](geterrorinfo.md)函数。
    
## <a name="requirements"></a>惠?  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** WMINet_Utils.idl  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>请参阅  
[WMI 和性能计数器 （非托管 API 参考）](index.md)
