---
title: ICLRDataTarget::SetThreadContext 方法
ms.date: 03/30/2017
api_name:
- ICLRDataTarget.SetThreadContext
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDataTarget::SetThreadContext
helpviewer_keywords:
- SetThreadContext method, ICLRDataTarget interface [.NET Framework debugging]
- ICLRDataTarget::SetThreadContext method [.NET Framework debugging]
ms.assetid: 103c8502-81fe-40d7-9c1e-9008d8fb19e1
topic_type:
- apiref
ms.openlocfilehash: d76a907434b12b85aaedeef169390ec6f0df724a
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79179131"
---
# <a name="iclrdatatargetsetthreadcontext-method"></a>ICLRDataTarget::SetThreadContext 方法
设置目标进程中指定线程的当前上下文。 此方法由通用语言运行时 （CLR） 数据访问服务调用。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT SetThreadContext (  
    [in] ULONG32            threadID,  
    [in] ULONG32            contextSize,  
    [in, size_is(contextSize)]
         BYTE               *context  
);  
```  
  
## <a name="parameters"></a>parameters  
 `threadID`  
 [在]目标进程中线程的操作系统标识符。  
  
 `contextSize`  
 [在]上下文的大小。  
  
 `context`  
 [在]指向包含上下文的缓冲区的指针。  
  
 缓冲区中`context`的数据将以 Win32`CONTEXT`结构的格式表示。 上下文指定特定于处理器的寄存器数据，因此 Win32`CONTEXT`结构的定义取决于处理器的体系结构。 有关 Win32`CONTEXT`结构的定义，请参阅 WinNT.h 标头文件。  
  
## <a name="remarks"></a>备注  
 此方法由调试应用程序的编写器实现。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标题：** ClrData.idl， ClrData.h  
  
 **库：** CorGuids.lib  
  
 **.NET 框架版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>另请参阅

- [ICLRDataTarget 接口](iclrdatatarget-interface.md)
