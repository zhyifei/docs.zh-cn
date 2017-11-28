---
title: "IMetaDataAssemblyEmit 接口"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataAssemblyEmit
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataAssemblyEmit
helpviewer_keywords: IMetaDataAssemblyEmit interface [.NET Framework metadata]
ms.assetid: 34fb03cc-2285-4a45-ac48-ad993b7a921a
topic_type: apiref
caps.latest.revision: "16"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: af7a5fd5a564aa7366924f47b0c526aff7153521
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataassemblyemit-interface"></a>IMetaDataAssemblyEmit 接口
提供支持公共语言运行时用于解析和使用资源的自描述模型的方法。  
  
## <a name="methods"></a>方法  
  
|方法|描述|  
|------------|-----------------|  
|[DefineAssembly 方法](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineassembly-method.md)|创建包含指定程序集的元数据的程序集数据结构，并返回关联的元数据标记。|  
|[DefineAssemblyRef 方法](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineassemblyref-method.md)|创建包含此程序集引用的程序集的元数据的 `AssemblyRef` 结构，并返回关联的元数据标记。|  
|[DefineExportedType 方法](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineexportedtype-method.md)|创建包含指定导出类型的元数据的 `ExportedType` 结构，并返回关联的元数据标记。|  
|[DefineFile 方法](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-definefile-method.md)|创建包含此程序集引用的程序集的元数据的 `File` 元数据结构，并返回关联的元数据标记。|  
|[DefineManifestResource 方法](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-definemanifestresource-method.md)|创建包含指定清单资源的元数据的 `ManifestResource` 结构，并返回关联的元数据标记。|  
|[SetAssemblyProps 方法](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-setassemblyprops-method.md)|修改指定的 `Assembly` 元数据结构。|  
|[SetAssemblyRefProps 方法](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-setassemblyrefprops-method.md)|修改指定的 `AssemblyRef` 元数据结构。|  
|[SetExportedTypeProps 方法](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-setexportedtypeprops-method.md)|修改指定的 `ExportedType` 元数据结构。|  
|[SetFileProps 方法](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-setfileprops-method.md)|修改指定的 `File` 元数据结构。|  
|[SetManifestResourceProps 方法](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-setmanifestresourceprops-method.md)|修改指定的 `ManifestResource` 元数据结构。|  
  
## <a name="remarks"></a>备注  
  
## <a name="requirements"></a>要求  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** Cor.h  
  
 **库：**用作 MsCorEE.dll 中的资源  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>另请参阅  
 [元数据接口](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)  
 [IMetaDataAssemblyImport 接口](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
