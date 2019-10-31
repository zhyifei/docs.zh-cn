---
title: IHostMalloc 接口
ms.date: 03/30/2017
api_name:
- IHostMAlloc
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostMAlloc
helpviewer_keywords:
- IHostMAlloc interface [.NET Framework hosting]
ms.assetid: e3c6643b-6fc7-4a99-959d-4b7b4e63fdee
topic_type:
- apiref
ms.openlocfilehash: abc6cca185b318be016f92ac8c97d21f7af5940a
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73136776"
---
# <a name="ihostmalloc-interface"></a>IHostMalloc 接口
提供允许公共语言运行时（CLR）通过宿主请求从堆进行细化分配的方法。  
  
## <a name="methods"></a>方法  
  
|方法|描述|  
|------------|-----------------|  
|[Alloc 方法](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-alloc-method.md)|请求宿主从堆分配请求的内存量。|  
|[DebugAlloc 方法](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-debugalloc-method.md)|请求宿主从堆分配请求的内存量，并另外跟踪内存的分配位置。|  
|[Free 方法](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-free-method.md)|释放使用 `Alloc` 方法分配的内存。|  
  
## <a name="remarks"></a>备注  
 CLR 通过调用[IHostMemoryManager：： CreateMalloc](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-createmalloc-method.md)方法获取指向 `IHostMalloc` 实例的接口指针。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** Mscoree.dll  
  
 **库：** 作为资源包括在 Mscoree.dll 中  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>请参阅

- [IHostMemoryManager 接口](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)
- [承载接口](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
