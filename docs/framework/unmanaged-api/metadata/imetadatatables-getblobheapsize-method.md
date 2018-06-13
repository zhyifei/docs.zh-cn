---
title: IMetaDataTables::GetBlobHeapSize 方法
ms.date: 03/30/2017
api_name:
- IMetaDataTables.GetBlobHeapSize
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables::GetBlobHeapSize
helpviewer_keywords:
- GetBlobHeapSize method [.NET Framework metadata]
- IMetaDataTables::GetBlobHeapSize method [.NET Framework metadata]
ms.assetid: 6330a9ee-8cd5-4299-86f1-b4de2c701a0d
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 787ea506c6698925473175cf7fdac340c0c2eca8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33447268"
---
# <a name="imetadatatablesgetblobheapsize-method"></a>IMetaDataTables::GetBlobHeapSize 方法
获取用字节表示，二进制大型对象 (BLOB) 堆的大小。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT GetBlobHeapSize (  
    [out] ULONG     *pcbBlobs  
);   
```  
  
#### <a name="parameters"></a>参数  
 `pcbBlobs`  
 [out]指向以字节为单位的 BLOB 堆的大小的指针。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** Cor.h  
  
 **库：** 用作 MsCorEE.dll 中的资源  
  
 **.NET framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>请参阅  
 [IMetaDataTables 接口](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)  
 [IMetaDataTables2 接口](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
