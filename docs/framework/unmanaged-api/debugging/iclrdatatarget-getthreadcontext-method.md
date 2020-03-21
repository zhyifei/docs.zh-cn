---
title: ICLRDataTarget::GetThreadContext 方法
ms.date: 03/30/2017
api_name:
- ICLRDataTarget.GetThreadContext
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDataTarget::GetThreadContext
helpviewer_keywords:
- ICLRDataTarget::GetThreadContext method [.NET Framework debugging]
- GetThreadContext method, ICLRDataTarget interface [.NET Framework debugging]
ms.assetid: b9d8c3b5-3a2e-4225-95d4-dd052c4532c3
topic_type:
- apiref
ms.openlocfilehash: 3777ad4b12c7d0593c095c470aba81088137a859
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79179184"
---
# <a name="iclrdatatargetgetthreadcontext-method"></a>ICLRDataTarget::GetThreadContext 方法
获取目标进程中给定线程的当前执行上下文。 此方法由通用语言运行时数据访问服务调用。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT GetThreadContext (  
    [in] ULONG32            threadID,  
    [in] ULONG32            contextFlags,  
    [in] ULONG32            contextSize,  
    [out, size_is(contextSize)]
        BYTE                *context  
);  
```  
  
## <a name="parameters"></a>parameters  
 `threadID`  
 [在]目标进程中线程的操作系统标识符。  
  
 `contextFlags`  
 [在]指定要返回上下文的哪些部分的标志。 实现将至少返回上下文的这些部分。  
  
 `contextSize`  
 [在]上下文的大小。  
  
 `context`  
 [出]指向要在其中放置上下文的缓冲区的指针。  
  
 缓冲区中`context`的数据必须采用 Win32`CONTEXT`结构的格式。 上下文指定特定于处理器的寄存器数据，因此 Win32`CONTEXT`结构的定义取决于处理器的体系结构。 有关 Win32`CONTEXT`结构的定义，请参阅 WinNT.h 标头文件。  
  
## <a name="remarks"></a>备注  
 此方法由调试应用程序的编写器实现。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标题：** ClrData.idl， ClrData.h  
  
 **库：** CorGuids.lib  
  
 **.NET 框架版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>另请参阅

- [ICLRDataTarget 接口](iclrdatatarget-interface.md)
