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
ms.openlocfilehash: 31be0525c637e50c1161129277d651b56dadfaa3
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/27/2020
ms.locfileid: "84006748"
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
  
## <a name="members"></a>成员  
  
|成员|描述|  
|------------|-----------------|  
|`dwAppDomainId`|的唯一标识符，该标识符由要从中 `IStream` 加载所引用的模块的[IHostAssemblyStore：:P rovidemodule](ihostassemblystore-providemodule-method.md)方法的调用返回。|  
|`lpAssemblyIdentity`|包含所引用的模块的程序集的唯一标识符。|  
|`lpModuleName`|引用的模块的名称。|  
  
## <a name="remarks"></a>备注  
 `ModuleBindInfo`作为参数传递给 `IHostAssemblyStore::ProvideModule` 。 宿主 `dwAppDomainId` 向公共语言运行时（CLR）提供唯一标识符。 调用[IHostAssemblyStore：:P rovideassembly](ihostassemblystore-provideassembly-method.md)方法返回后，运行时将使用标识符来确定是否已映射的内容 `IStream` 。 如果是这样，则运行时加载现有副本，而不是重新映射流。 运行时还会将此标识符用作从对方法的调用返回的流的查找密钥 `IHostAssemblyStore::ProvideAssembly` 。 因此，对于模块请求和程序集请求，标识符必须是唯一的。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。  
  
 **标头：** Mscoree.dll  
  
 **库：** 作为资源包括在 Mscoree.dll 中  
  
 **.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>另请参阅

- [承载结构](hosting-structures.md)
- [AssemblyBindInfo 结构](assemblybindinfo-structure.md)
- [ICLRAssemblyIdentityManager 接口](iclrassemblyidentitymanager-interface.md)
- [ICLRAssemblyReferenceList 接口](iclrassemblyreferencelist-interface.md)
- [IHostAssemblyManager 接口](ihostassemblymanager-interface.md)
