---
title: IHostAssemblyStore::ProvideModule 方法
ms.date: 03/30/2017
api_name:
- IHostAssemblyStore.ProvideModule
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostAssemblyStore::ProvideModule
helpviewer_keywords:
- IHostAssemblyStore::ProvideModule method [.NET Framework hosting]
- ProvideModule method [.NET Framework hosting]
ms.assetid: f42e3dd0-c88e-4748-b6c0-4c515a633180
topic_type:
- apiref
ms.openlocfilehash: eed09a8149a21140ad61133f29391f86cb0fb929
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73124475"
---
# <a name="ihostassemblystoreprovidemodule-method"></a>IHostAssemblyStore::ProvideModule 方法
解析程序集或链接的（但不是嵌入的）资源文件中的模块。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT ProvideModule (  
    [in]  ModuleBindInfo *pBindInfo,  
    [out] DWORD          *pdwModuleId,  
    [out] IStream        **ppStmModuleImage,  
    [out] IStream        **ppStmPDB  
);  
```  
  
## <a name="parameters"></a>参数  
 `pBindInfo`  
 中指向[ModuleBindInfo](../../../../docs/framework/unmanaged-api/hosting/modulebindinfo-structure.md)实例的指针，该实例描述请求的模块的 <xref:System.AppDomain>、程序集和模块名称。  
  
 `pdwModuleId`  
 弄一个指针，指向包含已加载模块的 `IStream` 的唯一标识符。  
  
 `ppStmModuleImage`  
 弄指向 `IStream` 对象（其中包含要加载的可移植可执行（PE）映像）的地址的指针; 如果找不到该模块，则为 null。  
  
 `ppStmPDB`  
 弄指向 `IStream` 对象的地址的指针，该对象包含请求的模块的程序调试（PDB）信息; 如果找不到 .pdb 文件，则为 null。  
  
## <a name="return-value"></a>返回值  
  
|HRESULT|描述|  
|-------------|-----------------|  
|S_OK|`ProvideModule` 成功返回。|  
|HOST_E_CLRNOTAVAILABLE|公共语言运行时（CLR）未加载到进程中，或 CLR 处于无法运行托管代码或成功处理调用的状态。|  
|HOST_E_TIMEOUT|调用超时。|  
|HOST_E_NOT_OWNER|调用方不拥有该锁。|  
|HOST_E_ABANDONED|已阻止的线程或纤程正在等待某个事件时，该事件被取消。|  
|E_FAIL|发生未知的灾难性故障。 当方法返回 E_FAIL 时，CLR 在该进程内将不再可用。 对宿主方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。|  
|COR_E_FILENOTFOUND （0x80070002）|找不到请求的程序集或链接的资源。|  
|E_NOT_SUFFICIENT_BUFFER|`pdwModuleId` 不够大，无法包含主机需要返回的标识符。|  
  
## <a name="remarks"></a>备注  
 为 `pdwModuleId` 返回的标识值由主机指定。 标识符在进程的生存期内必须是唯一的。 CLR 使用此值作为关联流的唯一标识符。 它会 `pAssemblyId` 根据对[ProvideAssembly](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-provideassembly-method.md)的调用返回的值以及对 `ProvideModule`的其他调用返回的 `pdwModuleId` 值来检查每个值。 如果主机为其他 `IStream`返回相同的标识符值，则 CLR 将检查是否已映射该流的内容。 如果是这样，CLR 将加载映像的现有副本，而不是映射一个新副本。 因此，标识符也不得与 `ProvideAssembly`返回的程序集标识符重叠。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** Mscoree.dll  
  
 **库：** 作为资源包括在 Mscoree.dll 中  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>请参阅

- [ICLRAssemblyReferenceList 接口](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)
- [IHostAssemblyManager 接口](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-interface.md)
- [IHostAssemblyStore 接口](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md)
