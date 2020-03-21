---
title: 获取多路复用Stub函数（非托管 API 引用）
description: GetDe多路复用Stub函数创建一个对象转发器接收器，以帮助客户端接收来自 Windows 管理的异步调用。
ms.date: 11/06/2017
api_name:
- GetDemultiplexedStub
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- GetDemultiplexedStub
helpviewer_keywords:
- GetDemultiplexedStub function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: d15fed261db2ca2cda6dbf824dc9cb0d5c56eed3
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79174961"
---
# <a name="getdemultiplexedstub-function"></a>GetDemultiplexedStub 函数
创建对象转发器接收器，帮助客户端从 Windows Management 接收异步调用。
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT GetDemultiplexedStub (
   [in] IUnknown*    pObject,
   [in] boolean      isLocal,
   [out] IUnknown**  ppObject
);
```  

## <a name="parameters"></a>parameters

`pObject`  
[在]指向客户端在进程中实现[IWbemObjectSink](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemobjectsink)的指针。

`isLocal`  
[在]指示事件是否为本地的标志 （`true`;否则， `false`.

`ppObject`  
[出]对象转发器接收器，用于帮助客户端接收来自 Windows 管理的异步调用。

## <a name="return-value"></a>返回值

如果函数成功，则返回值为`S_OK`（0）。

如果函数失败，返回值是非零错误代码。 要获取扩展的错误信息，请致电[GetErrorInfo](geterrorinfo.md)函数。

## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。  
  
 **标题：** WMINet_Utils.idl  
  
 **.NET 框架版本：**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>另请参阅

- [WMI 和性能计数器（非托管 API 参考）](index.md)
