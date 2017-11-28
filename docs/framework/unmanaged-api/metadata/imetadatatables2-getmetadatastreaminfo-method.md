---
title: "IMetaDataTables2::GetMetaDataStreamInfo 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataTables2.GetMetaDataStreamInfo
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataTables2::GetMetaDataStreamInfo
helpviewer_keywords:
- GetMetaDataStreamInfo method [.NET Framework metadata]
- IMetaDataTables2::GetMetaDataStreamInfo method [.NET Framework metadata]
ms.assetid: 8b280627-cc74-4789-95da-1fefc966de05
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: b1631ae8398a8daa910931ff705440a2be0cf21b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="imetadatatables2getmetadatastreaminfo-method"></a>IMetaDataTables2::GetMetaDataStreamInfo 方法
获取名称、 大小和元数据流的指定索引处的内容。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT GetMetaDataStreamInfo (  
   [in]  ULONG        ix,  
   [out] const char   **ppchName,  
   [out] const void   **ppv,  
   [out] ULONG        *pcb  
);  
```  
  
#### <a name="parameters"></a>参数  
 `ix`  
 [in]请求的元数据流的索引。  
  
 `ppchName`  
 [out]指向流的名称的指针。  
  
 `ppv`  
 [out]指向元数据流的指针。  
  
 `pcb`  
 [out]大小，以字节为单位的`ppv`。  
  
## <a name="requirements"></a>要求  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** Cor.h  
  
 **库：**用作 MsCorEE.dll 中的资源  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>另请参阅  
 [IMetaDataTables2 接口](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)  
 [IMetaDataTables 接口](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)
