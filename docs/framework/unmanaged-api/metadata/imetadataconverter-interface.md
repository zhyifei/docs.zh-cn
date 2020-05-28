---
title: IMetaDataConverter 接口
ms.date: 03/30/2017
api_name:
- IMetaDataConverter
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataConverter
helpviewer_keywords:
- IMetaDataConverter interface [.NET Framework metadata]
ms.assetid: 9caea662-0167-4267-b14a-2fa42c3be4ea
topic_type:
- apiref
ms.openlocfilehash: b6ca7c619d32e69ffac20b80561171d0320db2d4
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/27/2020
ms.locfileid: "84008373"
---
# <a name="imetadataconverter-interface"></a>IMetaDataConverter 接口
提供将类型库映射到其元数据签名并进行相互转换的方法。  
  
## <a name="methods"></a>方法  
  
|方法|说明|  
|------------|-----------------|  
|[GetMetaDataFromTypeInfo 方法](../../../../docs/framework/unmanaged-api/metadata/imetadataconverter-getmetadatafromtypeinfo-method.md)|获取一个指针，该指针指向表示指定实例引用的类型库的元数据签名的[IMetaDataImport](imetadataimport-interface.md)实例 `ITypeInfo` 。|  
|[GetMetaDataFromTypeLib 方法](imetadataconverter-getmetadatafromtypelib-method.md)|获取一个指针，该指针指向 `IMetaDataImport` 表示指定实例所表示的类型库的元数据签名的实例 `ITypeLib` 。|  
|[GetTypeLibFromMetaData 方法](imetadataconverter-gettypelibfrommetadata-method.md)|获取一个指向实例的指针，该 `ITypeLib` 对象表示具有指定模块和库名称的类型库。|  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。  
  
 **标头：** Cor  
  
 **库：** 用作 Mscoree.dll 中的资源  
  
 **.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>另请参阅

- [元数据接口](metadata-interfaces.md)
- [IMetaDataImport 接口](imetadataimport-interface.md)
