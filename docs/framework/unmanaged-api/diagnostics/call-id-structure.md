---
title: CALL_ID 结构
ms.date: 03/30/2017
api_name:
- CALL_ID
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- CALL_ID
helpviewer_keywords:
- CALL_ID structure [.NET Framework debugging]
ms.assetid: bfd46324-afec-4782-9c18-586d81fb4740
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: f8d6b16f3eeb32e41f3568e0b237f18c945a8cb8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33423892"
---
# <a name="callid-structure"></a>CALL_ID 结构
提供给正在调用的函数有关调试器的信息。 请参阅[INotifySink2](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-interface.md)有关详细信息的接口。  
  
## <a name="syntax"></a>语法  
  
```  
typedef struct tagCALL_ID  
{  
    LPCOLESTR       szMachine;  
    DWORD           dwPid;  
    USER_THREAD     *pUserThread;  
    STACK_ADDRESS   addrStackPointer;  
    LPCOLESTR       szEntryPoint;  
    LPCOLESTR       szDestinationMachine;  
} CALL_ID;  
```  
  
## <a name="members"></a>成员  
  
|成员|描述|  
|------------|-----------------|  
|`szMachine`|标识进行调用的计算机。|  
|`dwPid`|标识计算机处理器。|  
|`pUserThread`|标识正在执行调用的线程。|  
|`addrStackPointer`|指定的调用堆栈的地址。|  
|`szEntryPoint`|指定的调用的地址。|  
|`szDestinationMachine`|标识将执行调用的计算机。|  
  
## <a name="requirements"></a>要求  
 **标头：** ProtocolNotify2.idl  
  
## <a name="see-also"></a>请参阅  
 [INotifySink2 接口](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-interface.md)  
 [诊断符号存储区结构](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-structures.md)
