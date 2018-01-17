---
title: "IHostAssemblyStore::ProvideModule 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostAssemblyStore.ProvideModule
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostAssemblyStore::ProvideModule
helpviewer_keywords:
- IHostAssemblyStore::ProvideModule method [.NET Framework hosting]
- ProvideModule method [.NET Framework hosting]
ms.assetid: f42e3dd0-c88e-4748-b6c0-4c515a633180
topic_type: apiref
caps.latest.revision: "14"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 8b29f19933ae985d15627d1eba2622f350a52e72
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="ihostassemblystoreprovidemodule-method"></a>IHostAssemblyStore::ProvideModule 方法
解析程序集或链接 （而不是嵌入） 内的模块资源文件。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT ProvideModule (  
    [in]  ModuleBindInfo *pBindInfo,  
    [out] DWORD          *pdwModuleId,  
    [out] IStream        **ppStmModuleImage,  
    [out] IStream        **ppStmPDB  
);  
```  
  
#### <a name="parameters"></a>参数  
 `pBindInfo`  
 [in]指向的指针[ModuleBindInfo](../../../../docs/framework/unmanaged-api/hosting/modulebindinfo-structure.md)描述请求的模块的实例<xref:System.AppDomain>，程序集和模块名称。  
  
 `pdwModuleId`  
 [out]指向的唯一标识符的`IStream`包含加载的模块。  
  
 `ppStmModuleImage`  
 [out]指向的地址的指针`IStream`对象，其中包含要加载的可移植可执行 (PE) 映像，或如果未找到该模块则为 null。  
  
 `ppStmPDB`  
 [out]指向的地址的指针`IStream`对象，其中包含请求的模块中，与程序调试 (PDB) 信息或如果找不到.pdb 文件则为 null。  
  
## <a name="return-value"></a>返回值  
  
|HRESULT|描述|  
|-------------|-----------------|  
|S_OK|`ProvideModule`已成功返回。|  
|HOST_E_CLRNOTAVAILABLE|公共语言运行时 (CLR) 尚未加载到进程中，或 CLR 处于不能运行托管的代码或成功处理调用的状态。|  
|HOST_E_TIMEOUT|调用操作已超时。|  
|HOST_E_NOT_OWNER|调用方不拥有该锁。|  
|HOST_E_ABANDONED|事件已被取消时被阻塞的线程，或者纤程正在等待它。|  
|E_FAIL|出现未知的灾难性故障。 如果某方法返回 E_FAIL，CLR 不再可用进程内。 到托管方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。|  
|COR_E_FILENOTFOUND (0X80070002)|请求的程序集或链接的资源找不到。|  
|E_NOT_SUFFICIENT_BUFFER|`pdwModuleId`不大到足以包含主机想要返回的标识符。|  
  
## <a name="remarks"></a>备注  
 返回标识值`pdwModuleId`宿主指定。 标识符在进程的生存期内必须是唯一的。 CLR 使用此值关联的流作为唯一标识符。 它会检查每个值对的值`pAssemblyId`返回通过调用[ProvideAssembly](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-provideassembly-method.md)和的值针对`pdwModuleId`返回到其他调用`ProvideModule`。 如果主机的另一个返回相同的标识符值`IStream`，CLR 将检查是否已映射了该流的内容。 如果是这样，CLR 加载映像而不是映射一个新的现有副本。 因此，标识符也不能重叠从返回的程序集标识符`ProvideAssembly`。  
  
## <a name="requirements"></a>惠?  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** MSCorEE.h  
  
 **库：**作为 MSCorEE.dll 中的资源  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>请参阅  
 [ICLRAssemblyReferenceList 接口](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)  
 [IHostAssemblyManager 接口](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-interface.md)  
 [IHostAssemblyStore 接口](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md)
