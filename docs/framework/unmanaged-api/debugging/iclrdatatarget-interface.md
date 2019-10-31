---
title: ICLRDataTarget 接口
ms.date: 03/30/2017
api_name:
- ICLRDataTarget
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDataTarget
helpviewer_keywords:
- ICLRDataTarget interface [.NET Framework debugging]
ms.assetid: e2f05155-9bef-4e11-b703-7f05890665ca
topic_type:
- apiref
ms.openlocfilehash: 51b246e45b8bbdf809f5e90ac2bc29ca724751fc
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73113493"
---
# <a name="iclrdatatarget-interface"></a>ICLRDataTarget 接口
提供与公共语言运行时（CLR）的目标项交互的方法。  
  
## <a name="methods"></a>方法  
  
|方法|描述|  
|------------|-----------------|  
|[GetCurrentThreadID 方法](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-getcurrentthreadid-method.md)|获取当前线程的操作系统标识符。|  
|[GetImageBase 方法](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-getimagebase-method.md)|获取指定的图像的基本内存地址。|  
|[GetMachineType 方法](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-getmachinetype-method.md)|获取目标进程正在使用的指令集类型的标识符。|  
|[GetPointerSize 方法](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-getpointersize-method.md)|获取指向当前目标的指针的大小（以字节为单位）。|  
|[GetThreadContext 方法](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-getthreadcontext-method.md)|获取一个指针，该指针指向具有指定标识符的线程的上下文。|  
|[GetTLSValue 方法](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-gettlsvalue-method.md)|在线程本地存储（TLS）中获取指定线程的指定索引处的值。|  
|[ReadVirtual 方法](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-readvirtual-method.md)|将数据从指定的虚拟内存地址读入指定的缓冲区。|  
|[Request 方法](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-request-method.md)|由公共语言运行时（CLR）数据访问服务调用，用来请求操作，如实现所定义。|  
|[SetThreadContext 方法](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-setthreadcontext-method.md)|设置目标进程中指定线程的当前上下文。|  
|[SetTLSValue 方法](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-settlsvalue-method.md)|在目标进程中指定线程的线程本地存储（TLS）中设置一个值。|  
|[WriteVirtual 方法](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-writevirtual-method.md)|将数据从指定的缓冲区写入指定的虚拟内存地址。|  
  
## <a name="remarks"></a>备注  
 API 客户端（即调试器）必须根据特定目标项实现此接口。 例如，活动进程的实现将不同于内存转储的。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** ClrData，ClrData  
  
 **库：** CorGuids.lib  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>请参阅

- [ICLRDataTarget2 接口](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget2-interface.md)
- [调试接口](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
