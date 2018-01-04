---
title: "IMetaDataEmit2 接口"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataEmit2
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataEmit2
helpviewer_keywords: IMetaDataEmit2 interface [.NET Framework metadata]
ms.assetid: 866dc96b-bbfc-4c0f-80c2-38ce93072106
topic_type: apiref
caps.latest.revision: "14"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 94180a1f844ac43d8a42be59ac4fca807a70ec70
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataemit2-interface"></a>IMetaDataEmit2 接口
扩展[IMetaDataEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)主要是为了提供的功能，可以使用泛型类型的接口。  
  
## <a name="methods"></a>方法  
  
|方法|描述|  
|------------|-----------------|  
|[DefineGenericParam 方法](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-definegenericparam-method.md)|创建一个定义为泛型类型参数，并获取指向该泛型类型参数的标记。|  
|[DefineMethodSpec 方法](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-definemethodspec-method.md)|创建的泛型实例方法，并获取指向定义的标记。|  
|[GetDeltaSaveSize 方法](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-getdeltasavesize-method.md)|获取一个值，该值指示当前的编辑并继续会话 express 所做的更改所需的数据大小的差异。|  
|[ResetENCLog 方法](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-resetenclog-method.md)|重置的编辑并继续日志并将启动新会话。|  
|[SaveDelta 方法](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-savedelta-method.md)|将更改从当前的编辑并继续会话保存到指定的文件。|  
|[SaveDeltaToMemory 方法](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-savedeltatomemory-method.md)|将更改从当前的编辑并继续会话保存到内存中。|  
|[SaveDeltaToStream 方法](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-savedeltatostream-method.md)|将更改从当前的编辑并继续会话保存到指定的流。|  
|[SetGenericParamProps 方法](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-setgenericparamprops-method.md)|设置指定标记所引用的泛型参数定义的属性值。|  
  
## <a name="requirements"></a>惠?  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** Cor.h  
  
 **库：**用作 MsCorEE.dll 中的资源  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>请参阅  
 [元数据接口](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)  
 [IMetaDataEmit Interface](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
