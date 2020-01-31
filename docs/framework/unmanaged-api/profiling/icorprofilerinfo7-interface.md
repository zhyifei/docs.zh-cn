---
title: ICorProfilerInfo7 接口
ms.date: 03/30/2017
ms.assetid: cf37c462-73c5-412a-a7f8-bb26ca746313
ms.openlocfilehash: f80f310c10bae33583cb7cd2048ede4f5efbe14c
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/29/2020
ms.locfileid: "76861744"
---
# <a name="icorprofilerinfo7-interface"></a>ICorProfilerInfo7 接口
[仅在 .NET Framework 4.6.1 及更高版本中受支持]  
  
 [ICorProfilerInfo6](icorprofilerinfo6-interface.md)的子类，它提供了一种方法，用于将新定义的元数据应用于模块，并提供对内存中符号流的访问。  
  
## <a name="methods"></a>方法  
  
|方法|描述|  
|------------|-----------------|  
|[ApplyMetaData 方法](icorprofilerinfo7-applymetadata-method.md)|将 `IMetadataEmit::Define*` 方法新定义的元数据应用于指定的模块。|  
|[GetInMemorySymbolsLength 方法](icorprofilerinfo7-getinmemorysymbolslength-method.md)|返回内存中符号流的长度。|  
|[ReadInMemorySymbols](icorprofilerinfo7-readinmemorysymbols.md)|从内存中的符号流中读取字节。|  
  
## <a name="requirements"></a>需求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **头文件：** CorProf.idl、CorProf.h  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]  
  
## <a name="see-also"></a>另请参阅

- [Profiling 接口](profiling-interfaces.md)
