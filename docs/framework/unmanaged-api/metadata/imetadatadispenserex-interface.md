---
title: "IMetaDataDispenserEx 接口"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataDispenserEx
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataDispenserEx
helpviewer_keywords: IMetaDataDispenserEx interface [.NET Framework metadata]
ms.assetid: 78b3629e-77a2-4406-89c3-56b5cc2c4594
topic_type: apiref
caps.latest.revision: "14"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 5ecb4e94c0deed3ed62b2d2eb8b0309ca092abf8
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="imetadatadispenserex-interface"></a>IMetaDataDispenserEx 接口
扩展[IMetaDataDispenser 接口](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-interface.md)接口以提供的功能来控制对当前的元数据范围的元数据 Api 的进行操作。  
  
## <a name="methods"></a>方法  
  
|方法|描述|  
|------------|-----------------|  
|[FindAssembly 方法](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-findassembly-method.md)|未实现此方法。 如果调用，它将返回 E_NOTIMPL。|  
|[FindAssemblyModule 方法](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-findassemblymodule-method.md)|未实现此方法。 如果调用，它将返回 E_NOTIMPL。|  
|[GetCORSystemDirectory 方法](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-getcorsystemdirectory-method.md)|获取包含当前的公共语言运行时 (CLR) 的目录。 进程外调试器支持此方法仅供使用。 如果从另一个组件调用，它将返回 E_NOTIMPL。|  
|[GetOption 方法](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-getoption-method.md)|获取当前元数据范围的指定选项的值。 选项控制如何处理对当前的元数据范围的调用。|  
|[OpenScopeOnITypeInfo 方法](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-openscopeonitypeinfo-method.md)|未实现此方法。 如果调用，它将返回 E_NOTIMPL。|  
|[SetOption 方法](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-setoption-method.md)|将指定的选项设置为当前的元数据范围的给定值。 选项控制如何处理对当前的元数据范围的调用。|  
  
## <a name="requirements"></a>要求  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** Cor.h  
  
 **库：**用作 MsCorEE.dll 中的资源  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>另请参阅  
 [元数据接口](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)  
 [IMetaDataDispenser 接口](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-interface.md)  
 [IMetaDataEmit 接口](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [IMetaDataImport 接口](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
