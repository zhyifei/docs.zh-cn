---
title: ICLRTask2 接口
ms.date: 03/30/2017
api_name:
- ICLRTask2
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRTask2
helpviewer_keywords:
- ICLRTask2 interface [.NET Framework hosting]
ms.assetid: b5a22ebc-0582-49de-91f9-97a3d9789290
topic_type:
- apiref
ms.openlocfilehash: 47c6dd9045636bcfbe07c909fec3fda515d28ee8
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73124522"
---
# <a name="iclrtask2-interface"></a>ICLRTask2 接口
提供[ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)接口的所有功能;此外，还提供了允许线程中止在当前线程上延迟的方法。  
  
## <a name="methods"></a>方法  
  
|方法|描述|  
|------------|-----------------|  
|[BeginPreventAsyncAbort 方法](../../../../docs/framework/unmanaged-api/hosting/iclrtask2-beginpreventasyncabort-method.md)|延迟当前线程上的新线程中止请求。|  
|[EndPreventAsyncAbort 方法](../../../../docs/framework/unmanaged-api/hosting/iclrtask2-endpreventasyncabort-method.md)|允许新的或挂起的线程中止请求导致在当前线程上中止线程。|  
  
## <a name="remarks"></a>备注  
 `ICLRTask2` 接口继承了 `ICLRTask` 接口，并添加了允许主机延迟线程中止的方法，以保护不能失败的代码区域。 调用 `BeginPreventAsyncAbort` 会递增当前线程的延迟线程中止计数器，并调用 `EndPreventAsyncAbort` 减量。 对 `BeginPreventAsyncAbort` 和 `EndPreventAsyncAbort` 的调用可以嵌套。 只要计数器大于零，就会延迟当前线程的线程中止。  
  
 如果对 `BeginPreventAsyncAbort` 和 `EndPreventAsyncAbort` 的调用未配对，则可能会达到无法将线程中止传递到当前线程的状态。  
  
 此延迟不适用于自行中止的线程。  
  
 此功能公开的功能由虚拟机（VM）在内部使用。 滥用这些方法可能会导致 VM 中未指定的行为。 例如，如果不首先调用 `BeginPreventAsyncAbort` 调用 `EndPreventAsyncAbort` 可以将计数器设置为零。 同样，不检查内部计数器是否溢出。 如果它超过其整数限制，原因是主机和 VM 均递增，则未指定产生的行为。  
  
 有关从 `ICLRTask` 和此接口的其他用法继承的成员的信息，请参阅[ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)接口。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** Mscoree.dll  
  
 **库：** 作为资源包括在 Mscoree.dll 中  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>请参阅

- [ICLRTask 接口](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [ICLRTaskManager 接口](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [IHostTask 接口](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [IHostTaskManager 接口](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
- [承载接口](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
