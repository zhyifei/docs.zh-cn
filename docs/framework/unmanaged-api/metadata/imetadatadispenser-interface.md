---
title: "IMetaDataDispenser 接口"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataDispenser
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataDispenser
helpviewer_keywords: IMetaDataDispenser interface [.NET Framework metadata]
ms.assetid: 989840b3-9822-4ce5-a6c5-b375d3340a7a
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: c5a0464f2fb7b81d98fcbb4b04bc465cf57b1b0f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="imetadatadispenser-interface"></a>IMetaDataDispenser 接口
提供用于创建新的元数据范围，或打开一个现有方法。  
  
## <a name="methods"></a>方法  
  
|方法|描述|  
|------------|-----------------|  
|[DefineScope 方法](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-definescope-method.md)|你可以在其中创建新的元数据的内存中创建一个新的区域。|  
|[OpenScope 方法](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscope-method.md)|打开一个现有的磁盘上的文件并将其元数据映射到内存。|  
|[OpenScopeOnMemory 方法](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscopeonmemory-method.md)|将打开一个包含现有的元数据的内存区域。 也就是说，此方法打开的现有数据视为元数据的内存的指定的区域。|  
  
## <a name="requirements"></a>要求  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** Cor.h  
  
 **库：**用作 MsCorEE.dll 中的资源  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>另请参阅  
 [IMetaDataDispenserEx 接口](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-interface.md)  
 [元数据接口](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)
