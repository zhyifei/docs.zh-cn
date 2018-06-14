---
title: IHostAssemblyStore::ProvideAssembly 方法
ms.date: 03/30/2017
api_name:
- IHostAssemblyStore.ProvideAssembly
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostAssemblyStore::ProvideAssembly
helpviewer_keywords:
- ProvideAssembly method [.NET Framework hosting]
- IHostAssemblyStore::ProvideAssembly method [.NET Framework hosting]
ms.assetid: 625c3dd5-a3f0-442c-adde-310dadbb5054
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e32d48931177a42dd14092b4052370764a217abe
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33440358"
---
# <a name="ihostassemblystoreprovideassembly-method"></a>IHostAssemblyStore::ProvideAssembly 方法
获取未被引用程序集的引用[ICLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)从返回[ihostassemblymanager:: Getnonhoststoreassemblies](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-getnonhoststoreassemblies-method.md)。 公共语言运行时 (CLR) 调用`ProvideAssembly`列表中未显示每个程序集。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT ProvideAssembly (  
    [in]  AssemblyBindInfo *pBindInfo,  
    [out] UINT64           *pAssemblyId,  
    [out] UINT64           *pHostContext,  
    [out] IStream          **ppStmAssemblyImage,  
    [out] IStream          **ppStmPDB  
);  
```  
  
#### <a name="parameters"></a>参数  
 `pBindInfo`  
 [in]指向的指针[AssemblyBindInfo](../../../../docs/framework/unmanaged-api/hosting/assemblybindinfo-structure.md)主机使用来确定是否存在任何版本控制策略，包括某些绑定特征的实例和要绑定到的程序集。  
  
 `pAssemblyId`  
 [out]指向此请求的程序集的唯一标识符的`IStream`。  
  
 `pHostContext`  
 [out]用于确定请求的程序集而无需平台的证据的特定于宿主的数据的指针调用。 `pHostContext` 对应于<xref:System.Reflection.Assembly.HostContext%2A>属性托管的<xref:System.Reflection.Assembly>类。  
  
 `ppStmAssemblyImage`  
 [out]指向的地址的指针`IStream`包含要加载的或如果找不到程序集为 null 的可移植可执行 (PE) 映像。  
  
 `ppStmPDB`  
 [out]指向的地址的指针`IStream`如果找不到.pdb 文件包含的程序调试 (PDB) 信息或为 null。  
  
## <a name="return-value"></a>返回值  
  
|HRESULT|描述|  
|-------------|-----------------|  
|S_OK|`ProvideAssembly` 已成功返回。|  
|HOST_E_CLRNOTAVAILABLE|CLR 尚未加载到进程中，或 CLR 处于不能运行托管的代码或成功处理调用的状态。|  
|HOST_E_TIMEOUT|调用操作已超时。|  
|HOST_E_NOT_OWNER|调用方不拥有该锁。|  
|HOST_E_ABANDONED|事件已被取消时被阻塞的线程，或者纤程正在等待它。|  
|E_FAIL|出现未知的灾难性故障。 如果某方法返回 E_FAIL，CLR 不再可用进程内。 到托管方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。|  
|COR_E_FILENOTFOUND (0X80070002)|找不到请求的程序集。|  
|E_NOT_SUFFICIENT_BUFFER|通过指定的缓冲区大小`pAssemblyId`不足够大以保存主机想要返回的标识符。|  
  
## <a name="remarks"></a>备注  
 返回标识值`pAssemblyId`宿主指定。 标识符在进程的生存期内必须是唯一的。 CLR 使用此值流作为唯一标识符。 它会检查每个值对的值`pAssemblyId`返回到其他调用`ProvideAssembly`。 如果主机返回相同`pAssemblyId`另一项的值`IStream`，CLR 将检查是否已映射了该流的内容。 如果是这样，则运行时将加载映像而不是映射一个新的现有副本。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** MSCorEE.h  
  
 **库：** 作为 MSCorEE.dll 中的资源  
  
 **.NET framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>请参阅  
 [ICLRAssemblyReferenceList 接口](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)  
 [IHostAssemblyManager 接口](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-interface.md)  
 [IHostAssemblyStore 接口](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md)
