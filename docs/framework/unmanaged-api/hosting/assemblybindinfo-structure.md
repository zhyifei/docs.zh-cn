---
title: AssemblyBindInfo 结构
ms.date: 03/30/2017
api_name:
- AssemblyBindInfo
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- AssemblyBindInfo
helpviewer_keywords:
- AssemblyBindInfo structure [.NET Framework hosting]
ms.assetid: 6fc01e98-c2e7-49de-ab9f-95937cc89017
topic_type:
- apiref
ms.openlocfilehash: 8764a3d665c997460419561eb168f92ca769c30c
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73192116"
---
# <a name="assemblybindinfo-structure"></a>AssemblyBindInfo 结构
提供有关所引用程序集的详细信息。  
  
## <a name="syntax"></a>语法  
  
```cpp  
typedef struct _AssemblyBindInfo {  
    DWORD       dwAppDomainId;  
    LPCWSTR     lpReferencedIdentity;  
    LPCWSTR     lpPostPolicyIdentity;  
    DWORD       ePolicyLevel;  
} AssemblyBindInfo;  
```  
  
## <a name="members"></a>Members  
  
|成员|描述|  
|------------|-----------------|  
|`dwAppDomainId`|调用[IHostAssemblyStore：:P rovideassembly](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-provideassembly-method.md)的调用所返回的 `IStream` 的唯一标识符，将从中加载所引用的程序集。|  
|`lpReferencedIdentity`|所引用程序集的唯一标识符。|  
|`lpPostPolicyIdentity`|在应用任何绑定策略值之后引用的程序集的标识符。|  
|`ePolicyLevel`|[EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md)值之一，指示应将哪些版本控制策略应用于所引用的程序集。|  
  
## <a name="remarks"></a>备注  
 宿主向公共语言运行时（CLR） `dwAppDomainId` 提供唯一标识符。 在对 `IHostAssemblyStore::ProvideAssembly` 的调用返回后，运行时将使用标识符来确定是否已映射 `IStream` 的内容。 如果是这样，则运行时加载现有副本，而不是重新映射流。 运行时还会将此标识符用作从对[IHostAssemblyStore：:P rovidemodule](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-providemodule-method.md)的调用返回的流的查找密钥。 因此，对于模块请求和程序集请求，标识符必须是唯一的。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** Mscoree.dll  
  
 **库：** 作为资源包括在 Mscoree.dll 中  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>请参阅

- [承载结构](../../../../docs/framework/unmanaged-api/hosting/hosting-structures.md)
- [ICLRAssemblyIdentityManager 接口](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)
- [ICLRAssemblyReferenceList 接口](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)
- [IHostAssemblyManager 接口](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-interface.md)
- [IHostAssemblyStore 接口](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md)
- [ModuleBindInfo 结构](../../../../docs/framework/unmanaged-api/hosting/modulebindinfo-structure.md)
