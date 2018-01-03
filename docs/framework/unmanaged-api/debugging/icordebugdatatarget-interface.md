---
title: "ICorDebugDataTarget 接口"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugDataTarget
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugDataTarget
helpviewer_keywords: ICorDebugDataTarget interface [.NET Framework debugging]
ms.assetid: df5f05be-bed7-4f3c-bc89-dbb435d79a0b
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: b5d3a3b190cfa606bd4239e24c5defdaff9f4257
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugdatatarget-interface"></a>ICorDebugDataTarget 接口
提供一个回调接口，该接口可提供对特定目标进程的访问。  
  
## <a name="methods"></a>方法  
  
|方法|描述|  
|------------|-----------------|  
|[GetPlatform 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-getplatform-method.md)|提供有关平台，包括处理器体系结构和目标进程正在其运行的操作系统的信息。|  
|[ReadVirtual 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-readvirtual-method.md)|获取指定的地址处开始的连续内存块，并在提供的缓冲区中将其返回。|  
|[GetThreadContext 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-getthreadcontext-method.md)|请求指定的线程的当前线程上下文。|  
  
## <a name="remarks"></a>备注  
 `ICorDebugDataTarget`和其方法具有以下特征：  
  
-   调试服务对此接口可访问内存和目标进程中的其他数据调用方法。  
  
-   调试器客户端必须实现此接口为适合特定的目标 （例如，活动进程或内存转储）。  
  
-   `ICorDebugDataTarget`方法可以在其他实现的方法内调用只能从`ICorDebug*`接口。 这可确保调试器客户端已通过的线程调用，以及何时进行控制。  
  
-   `ICorDebugDataTarget`实现必须始终返回有关目标的最新信息。  
  
 应停止目标进程，并将其以任何方式时不更改`ICorDebug*`接口 (并因此`ICorDebugDataTarget`方法) 正被调用。 如果目标为活动的进程并且其状态更改， [iclrdebugging:: Openvirtualprocess](../../../../docs/framework/unmanaged-api/debugging/iclrdebugging-openvirtualprocess-method.md)方法必须再次调用提供的替换 ICorDebugProcess 实例。  
  
> [!NOTE]
>  此接口不支持跨计算机或跨进程远程调用。  
  
## <a name="requirements"></a>惠?  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** CorDebug.idl、 CorDebug.h  
  
 **库：** CorGuids.lib  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>请参阅  
 [调试接口](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [调试](../../../../docs/framework/unmanaged-api/debugging/index.md)
