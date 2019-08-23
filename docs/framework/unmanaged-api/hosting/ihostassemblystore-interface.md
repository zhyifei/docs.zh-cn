---
title: IHostAssemblyStore 接口
ms.date: 03/30/2017
api_name:
- IHostAssemblyStore
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostAssemblyStore
helpviewer_keywords:
- IHostAssemblyStore interface [.NET Framework hosting]
ms.assetid: cccb650f-abe0-41e2-9fd1-b383788eb1f6
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f881440b2e93745723bd090cfbab0286dcd0a4e5
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69937877"
---
# <a name="ihostassemblystore-interface"></a>IHostAssemblyStore 接口
提供允许主机独立于公共语言运行时 (CLR) 加载程序集和模块的方法。  
  
## <a name="methods"></a>方法  
  
|方法|描述|  
|------------|-----------------|  
|[ProvideAssembly 方法](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-provideassembly-method.md)|获取对[IHostAssemblyManager:: GetNonHostStoreAssemblies](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-getnonhoststoreassemblies-method.md)调用返回的[ICLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)未引用的程序集的引用。|  
|[ProvideModule 方法](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-providemodule-method.md)|解析程序集或链接 (而非嵌入) 资源文件中的模块。|  
  
## <a name="remarks"></a>备注  
 `IHostAssemblyStore`提供一种方法, 使主机可以根据程序集标识有效地加载程序集。 宿主通过返回`IStream`直接指向字节的实例来加载程序集。  
  
 CLR 通过在初始化时调用`IHostAssemblyStore` `IHostAssemblyManager::GetNonHostAssemblyStores`来确定宿主是否已实现。 例如, 这允许主机控制与用户程序集的绑定, 但要依赖于运行时绑定到 .NET Framework 程序集。  
  
> [!NOTE]
> 在提供的`IHostAssemblyStore`实现中, 主机指定其意图以解析从`IHostAssemblyManager::GetNonHostStoreAssemblies`返回的`ICLRAssemblyReferenceList`未引用的所有程序集。  
  
> [!NOTE]
> .NET Framework 版本2.0 不为宿主提供一种方法来加载程序集的本机映像, 如[本机映像生成器 (ngen.exe)](../../../../docs/framework/tools/ngen-exe-native-image-generator.md)实用程序所提供。  
  
## <a name="requirements"></a>要求  
 **适用**请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** MSCorEE.h  
  
 **类库**作为资源包括在 Mscoree.dll 中  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>请参阅

- [ICLRAssemblyReferenceList 接口](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)
- [IHostAssemblyManager 接口](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-interface.md)
- [承载接口](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
