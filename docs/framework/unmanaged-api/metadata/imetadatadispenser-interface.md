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
ms.workload: dotnet
ms.openlocfilehash: 678796357b36beb26ebbf34edc713ff6f15a7c40
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="imetadatadispenser-interface"></a>IMetaDataDispenser 接口
提供用于创建新的元数据范围，或打开一个现有方法。  
  
## <a name="methods"></a>方法  
  
|方法|描述|  
|------------|-----------------|  
|[DefineScope 方法](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-definescope-method.md)|你可以在其中创建新的元数据的内存中创建一个新的区域。|  
|[OpenScope 方法](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscope-method.md)|打开一个现有的磁盘上的文件并将其元数据映射到内存。|  
|[OpenScopeOnMemory 方法](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscopeonmemory-method.md)|将打开一个包含现有的元数据的内存区域。 也就是说，此方法打开的现有数据视为元数据的内存的指定的区域。|  
  
## <a name="requirements"></a>惠?  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** Cor.h  
  
 **库：**用作 MsCorEE.dll 中的资源  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>请参阅  
 [IMetaDataDispenserEx 接口](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-interface.md)  
 [元数据接口](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)
