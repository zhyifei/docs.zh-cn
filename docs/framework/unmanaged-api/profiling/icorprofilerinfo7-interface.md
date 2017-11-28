---
title: "ICorProfilerInfo7 接口"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: cf37c462-73c5-412a-a7f8-bb26ca746313
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 2a85bf82a01f431e42a5714eeb54e17a34314534
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="icorprofilerinfo7-interface"></a>ICorProfilerInfo7 接口
[支持版本：[!INCLUDE[net_v461](../../../../includes/net-v461-md.md)] 及更高版本]  
  
 一个子类[ICorProfilerInfo6](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo6-interface.md) ，它提供了新应用的方法定义模块的元数据使您可以访问的内存中的符号流。  
  
## <a name="methods"></a>方法  
  
|方法|描述|  
|------------|-----------------|  
|[ApplyMetaData 方法](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo7-applymetadata-method.md)|将应用新定义的元数据`IMetadataEmit::Define*`到指定的模块的方法。|  
|[GetInMemorySymbolsLength 方法](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo7-getinmemorysymbolslength-method.md)|返回的内存中的符号流的长度。|  
|[ReadInMemorySymbols](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo7-readinmemorysymbols.md)|从内存中的符号流读取字节。|  
  
## <a name="requirements"></a>要求  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **头文件：** CorProf.idl、CorProf.h  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]  
  
## <a name="see-also"></a>另请参阅  
 [分析接口](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
