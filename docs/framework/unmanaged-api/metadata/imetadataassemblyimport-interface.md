---
title: "IMetaDataAssemblyImport 接口"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataAssemblyImport
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataAssemblyImport
helpviewer_keywords: IMetaDataAssemblyImport interface [.NET Framework metadata]
ms.assetid: 29c6fba5-4cea-417d-b484-7ed22ebff1c9
topic_type: apiref
caps.latest.revision: "13"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: ef5b913dc9b1391c63cb123e1f922ca61da6a5bb
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataassemblyimport-interface"></a>IMetaDataAssemblyImport 接口
提供访问和检查程序集清单内容的方法。  
  
## <a name="methods"></a>方法  
  
|方法|描述|  
|------------|-----------------|  
|[CloseEnum 方法](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-closeenum-method.md)|释放指定的枚举的句柄。|  
|[EnumAssemblyRefs 方法](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-enumassemblyrefs-method.md)|获取枚举数，其中包含的接口指针`mdAssemblyRef`由当前的元数据范围内的程序集引用的程序集的令牌。|  
|[EnumExportedTypes 方法](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-enumexportedtypes-method.md)|获取枚举数，其中包含的接口指针`mdExportedType`由当前的元数据范围内的程序集引用的 COM 类型的令牌。|  
|[EnumFiles 方法](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-enumfiles-method.md)|获取枚举数，其中包含的接口指针`mdFile`由当前的元数据范围内的程序集所引用的文件的令牌。|  
|[EnumManifestResources 方法](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-enummanifestresources-method.md)|获取枚举数，其中包含的接口指针`mdManifestResource`由当前的元数据范围内的程序集引用的资源的令牌。|  
|[FindAssembliesByName 方法](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-findassembliesbyname-method.md)|获取一个数组`mdAssemblyRef`具有指定名称的程序集的令牌。|  
|[FindExportedTypeByName 方法](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-findexportedtypebyname-method.md)|获取`mdExportedType`标记，表示具有指定名称的 COM 类型。|  
|[FindManifestResourceByName 方法](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-findmanifestresourcebyname-method.md)|获取`mdManifestResource`标记，表示具有指定名称的资源。|  
|[GetAssemblyFromScope 方法](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-getassemblyfromscope-method.md)|当前的元数据范围内获取程序集的令牌。|  
|[GetAssemblyProps 方法](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-getassemblyprops-method.md)|获取指定的程序集的属性设置。|  
|[GetAssemblyRefProps 方法](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-getassemblyrefprops-method.md)|获取指定的属性设置`mdAssemblyRef`令牌。|  
|[GetExportedTypeProps 方法](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-getexportedtypeprops-method.md)|获取指定的 COM 类型的属性设置。|  
|[GetFileProps 方法](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-getfileprops-method.md)|获取指定的文件的属性设置。|  
|[GetManifestResourceProps 方法](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-getmanifestresourceprops-method.md)|获取指定的清单资源的属性设置。|  
  
## <a name="requirements"></a>要求  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** Cor.h  
  
 **库：**用作 MsCorEE.dll 中的资源  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>另请参阅  
 [元数据接口](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)  
 [IMetaDataAssemblyEmit 接口](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
