---
title: "IMetaDataError 接口"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataError
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataError
helpviewer_keywords: IMetaDataError interface [.NET Framework metadata]
ms.assetid: 0020b62c-ea88-40c7-a9ee-16b064f81624
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 9ae90221a1b305fdf09ae9583e720a2092289362
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="imetadataerror-interface"></a>IMetaDataError 接口
提供用于元数据合并期间报告错误的回调机制。  
  
> [!NOTE]
>  `IMetaDataError`由客户端必须实现接口。  
  
## <a name="methods"></a>方法  
  
|方法|描述|  
|------------|-----------------|  
|[OnError 方法](../../../../docs/framework/unmanaged-api/metadata/imetadataerror-onerror-method.md)|提供在元数据合并过程中发生的错误的通知。|  
  
## <a name="requirements"></a>要求  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** Cor.h  
  
 **库：**用作 MsCorEE.dll 中的资源  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>另请参阅  
 [元数据接口](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)
