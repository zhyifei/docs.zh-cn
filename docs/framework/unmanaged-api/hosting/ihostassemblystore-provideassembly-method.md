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
ms.openlocfilehash: a93d700c9c398076d87156cd2eb9c6d0d08cccfd
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73124490"
---
# <a name="ihostassemblystoreprovideassembly-method"></a>IHostAssemblyStore::ProvideAssembly 方法
获取对程序集的引用，该程序集未由从[IHostAssemblyManager：： GetNonHostStoreAssemblies](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-getnonhoststoreassemblies-method.md)返回的[ICLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)引用。 公共语言运行时（CLR）对列表中未显示的每个程序集调用 `ProvideAssembly`。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT ProvideAssembly (  
    [in]  AssemblyBindInfo *pBindInfo,  
    [out] UINT64           *pAssemblyId,  
    [out] UINT64           *pHostContext,  
    [out] IStream          **ppStmAssemblyImage,  
    [out] IStream          **ppStmPDB  
);  
```  
  
## <a name="parameters"></a>参数  
 `pBindInfo`  
 中指向[AssemblyBindInfo](../../../../docs/framework/unmanaged-api/hosting/assemblybindinfo-structure.md)实例的指针，主机使用该实例来确定特定的绑定特征，包括是否存在任何版本控制策略以及要绑定到的程序集。  
  
 `pAssemblyId`  
 弄一个指针，指向该 `IStream`所请求的程序集的唯一标识符。  
  
 `pHostContext`  
 弄指向特定于主机的数据的指针，用于在不需要平台调用的情况下确定请求的程序集的证据。 `pHostContext` 对应于托管 <xref:System.Reflection.Assembly> 类的 <xref:System.Reflection.Assembly.HostContext%2A> 属性。  
  
 `ppStmAssemblyImage`  
 弄指向包含要加载的可移植可执行（PE）映像的 `IStream` 的地址的指针; 如果找不到该程序集，则为 null。  
  
 `ppStmPDB`  
 弄指向包含程序调试（PDB）信息的 `IStream` 的地址的指针; 如果找不到 .pdb 文件，则为 null。  
  
## <a name="return-value"></a>返回值  
  
|HRESULT|描述|  
|-------------|-----------------|  
|S_OK|`ProvideAssembly` 成功返回。|  
|HOST_E_CLRNOTAVAILABLE|CLR 未加载到进程中，或 CLR 处于无法运行托管代码或成功处理调用的状态。|  
|HOST_E_TIMEOUT|调用超时。|  
|HOST_E_NOT_OWNER|调用方不拥有该锁。|  
|HOST_E_ABANDONED|已阻止的线程或纤程正在等待某个事件时，该事件被取消。|  
|E_FAIL|发生未知的灾难性故障。 当方法返回 E_FAIL 时，CLR 在该进程内将不再可用。 对宿主方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。|  
|COR_E_FILENOTFOUND （0x80070002）|找不到请求的程序集。|  
|E_NOT_SUFFICIENT_BUFFER|`pAssemblyId` 指定的缓冲区大小不够大，无法容纳主机需要返回的标识符。|  
  
## <a name="remarks"></a>备注  
 为 `pAssemblyId` 返回的标识值由主机指定。 标识符在进程的生存期内必须是唯一的。 CLR 使用此值作为流的唯一标识符。 它会对照 `ProvideAssembly`的其他调用返回的 `pAssemblyId` 的值检查每个值。 如果主机返回其他 `IStream`的相同 `pAssemblyId` 值，则 CLR 将检查是否已映射该流的内容。 如果是这样，则运行时加载映像的现有副本，而不是映射一个新副本。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** Mscoree.dll  
  
 **库：** 作为资源包括在 Mscoree.dll 中  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>请参阅

- [ICLRAssemblyReferenceList 接口](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)
- [IHostAssemblyManager 接口](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-interface.md)
- [IHostAssemblyStore 接口](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md)
