---
title: IMetaDataAssemblyImport 接口
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyImport
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyImport
helpviewer_keywords:
- IMetaDataAssemblyImport interface [.NET Framework metadata]
ms.assetid: 29c6fba5-4cea-417d-b484-7ed22ebff1c9
topic_type:
- apiref
ms.openlocfilehash: 289e26868ff2eb9e1d97cf084e9a888815062ea4
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74436304"
---
# <a name="imetadataassemblyimport-interface"></a>IMetaDataAssemblyImport 接口
提供访问和检查程序集清单内容的方法。  
  
## <a name="methods"></a>方法  
  
|方法|说明|  
|------------|-----------------|  
|[CloseEnum 方法](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-closeenum-method.md)|释放到指定枚举器的句柄。|  
|[EnumAssemblyRefs 方法](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-enumassemblyrefs-method.md)|获取一个指向枚举数的接口指针，该枚举数包含当前元数据范围内的程序集所引用的程序集的 `mdAssemblyRef` 标记。|  
|[EnumExportedTypes 方法](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-enumexportedtypes-method.md)|获取一个指向枚举数的接口指针，该枚举数包含当前元数据范围内的程序集引用的 COM 类型的 `mdExportedType` 标记。|  
|[EnumFiles 方法](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-enumfiles-method.md)|获取一个指向枚举数的接口指针，该枚举数包含当前元数据范围内的程序集所引用的文件的 `mdFile` 标记。|  
|[EnumManifestResources 方法](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-enummanifestresources-method.md)|获取一个指向枚举数的接口指针，该枚举数包含当前元数据范围内的程序集所引用资源的 `mdManifestResource` 标记。|  
|[FindAssembliesByName 方法](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-findassembliesbyname-method.md)|获取具有指定名称的程序集的 `mdAssemblyRef` 标记的数组。|  
|[FindExportedTypeByName 方法](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-findexportedtypebyname-method.md)|获取具有指定名称的 COM 类型的 `mdExportedType` 标记。|  
|[FindManifestResourceByName 方法](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-findmanifestresourcebyname-method.md)|获取具有指定名称的资源的 `mdManifestResource` 标记。|  
|[GetAssemblyFromScope 方法](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-getassemblyfromscope-method.md)|获取当前元数据范围内的程序集的标记。|  
|[GetAssemblyProps 方法](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-getassemblyprops-method.md)|获取指定程序集的属性设置。|  
|[GetAssemblyRefProps 方法](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-getassemblyrefprops-method.md)|获取指定 `mdAssemblyRef` 标记的属性设置。|  
|[GetExportedTypeProps 方法](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-getexportedtypeprops-method.md)|获取指定 COM 类型的属性设置。|  
|[GetFileProps 方法](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-getfileprops-method.md)|获取指定文件的属性设置。|  
|[GetManifestResourceProps 方法](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-getmanifestresourceprops-method.md)|获取指定的清单资源的属性设置。|  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** Cor  
  
 **库：** 用作 Mscoree.dll 中的资源  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>另请参阅

- [元数据接口](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)
- [IMetaDataAssemblyEmit 接口](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
