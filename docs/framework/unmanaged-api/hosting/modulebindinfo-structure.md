---
title: ModuleBindInfo 结构
ms.date: 03/30/2017
api_name:
- ModuleBindInfo
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ModuleBindInfo
helpviewer_keywords:
- ModuleBindInfo structure [.NET Framework hosting]
ms.assetid: 632d4adc-dbc9-4ce8-9397-abc3285c1c69
topic_type:
- apiref
ms.openlocfilehash: ae40d8adaae70ccff6e8058858a506267d58873f
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73133750"
---
# <a name="modulebindinfo-structure"></a>ModuleBindInfo 结构
提供有关被引用模块和包含它的程序集的详细信息。  
  
## <a name="syntax"></a>语法  
  
```cpp  
typedef struct _ModuleBindInfo {  
    DWORD    dwAppDomainId;  
    LPCWSTR  lpAssemblyIdentity;  
    LPCWSTR  lpModuleName  
} ModuleBindInfo;  
```  
  
## <a name="members"></a>Members  
  
|成员|描述|  
|------------|-----------------|  
|`dwAppDomainId`|`IStream` 的唯一标识符，该标识符由要从中加载所引用的模块的[IHostAssemblyStore：:P rovidemodule](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-providemodule-method.md)方法的调用返回。|  
|`lpAssemblyIdentity`|包含所引用的模块的程序集的唯一标识符。|  
|`lpModuleName`|引用的模块的名称。|  
  
## <a name="remarks"></a>备注  
 `ModuleBindInfo` 作为参数传递给 `IHostAssemblyStore::ProvideModule`。 宿主向公共语言运行时（CLR） `dwAppDomainId` 提供唯一标识符。 调用[IHostAssemblyStore：:P rovideassembly](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-provideassembly-method.md)方法返回后，运行时将使用标识符来确定是否已映射 `IStream` 的内容。 如果是这样，则运行时加载现有副本，而不是重新映射流。 运行时还会将此标识符用作从调用 `IHostAssemblyStore::ProvideAssembly` 方法返回的流的查找密钥。 因此，对于模块请求和程序集请求，标识符必须是唯一的。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** Mscoree.dll  
  
 **库：** 作为资源包括在 Mscoree.dll 中  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>请参阅

- [承载结构](../../../../docs/framework/unmanaged-api/hosting/hosting-structures.md)
- [AssemblyBindInfo 结构](../../../../docs/framework/unmanaged-api/hosting/assemblybindinfo-structure.md)
- [ICLRAssemblyIdentityManager 接口](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)
- [ICLRAssemblyReferenceList 接口](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)
- [IHostAssemblyManager 接口](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-interface.md)
