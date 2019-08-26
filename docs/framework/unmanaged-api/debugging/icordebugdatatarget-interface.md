---
title: ICorDebugDataTarget 接口
ms.date: 03/30/2017
api_name:
- ICorDebugDataTarget
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugDataTarget
helpviewer_keywords:
- ICorDebugDataTarget interface [.NET Framework debugging]
ms.assetid: df5f05be-bed7-4f3c-bc89-dbb435d79a0b
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0c6a8ee1bcc65e640ef871e57acdeef21acd7896
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69930825"
---
# <a name="icordebugdatatarget-interface"></a>ICorDebugDataTarget 接口
提供一个回调接口，该接口可提供对特定目标进程的访问。  
  
## <a name="methods"></a>方法  
  
|方法|描述|  
|------------|-----------------|  
|[GetPlatform 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-getplatform-method.md)|提供有关平台的信息, 包括在其上运行目标进程的处理器体系结构和操作系统。|  
|[ReadVirtual 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-readvirtual-method.md)|获取从指定地址开始的连续内存块, 并将其返回到提供的缓冲区中。|  
|[GetThreadContext 方法](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-getthreadcontext-method.md)|请求指定线程的当前线程上下文。|  
  
## <a name="remarks"></a>备注  
 `ICorDebugDataTarget`及其方法具有以下特征:  
  
- 调试服务调用此接口上的方法以访问目标进程中的内存和其他数据。  
  
- 调试器客户端必须根据特定目标 (例如, 实时进程或内存转储) 实现此接口。  
  
- 只能从其他`ICorDebug*`接口实现的方法中调用方法。`ICorDebugDataTarget` 这确保了调试器客户端可以控制调用它的线程和时间。  
  
- `ICorDebugDataTarget`实现必须始终返回有关目标的最新信息。  
  
 如果调用了`ICorDebug*`接口 (和因此`ICorDebugDataTarget`方法), 则目标进程应停止并且不以任何方式更改。 如果目标是实时进程并且其状态发生更改, 则必须再次调用[ICLRDebugging:: OpenVirtualProcess](../../../../docs/framework/unmanaged-api/debugging/iclrdebugging-openvirtualprocess-method.md)方法以提供替换 ICorDebugProcess 实例。  
  
> [!NOTE]
> 此接口不支持跨计算机或跨进程远程调用。  
  
## <a name="requirements"></a>要求  
 **适用**请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** Cordebug.idl, Cordebug.idl  
  
 **类库**CorGuids.lib  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>请参阅

- [调试接口](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [调试](../../../../docs/framework/unmanaged-api/debugging/index.md)
