---
title: "IMetaDataEmit2::DefineMethodSpec 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataEmit2.DefineMethodSpec
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataEmit2::DefineMethodSpec
helpviewer_keywords:
- DefineMethodSpec method [.NET Framework metadata]
- IMetaDataEmit2::DefineMethodSpec method [.NET Framework metadata]
ms.assetid: 3c24e552-fc69-4971-b65a-a3e4b5f7f1e8
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 036654c733dc73d40c526bf5cad4dd3750e2e9d6
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataemit2definemethodspec-method"></a>IMetaDataEmit2::DefineMethodSpec 方法
创建的泛型实例方法，并获取指向定义的标记。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT DefineMethodSpec (  
    [in]  mdToken           tkParent,   
    [in]  PCCOR_SIGNATURE   pvSigBlob,   
    [in]  ULONG             cbSigBlob,   
    [out] mdMethodSpec      *pmi  
);  
```  
  
#### <a name="parameters"></a>参数  
 `tkParent`  
 [in]要创建泛型实例方法标记。 令牌的类型必须为`mdMethodDef`或`mdMemberRef`。  
  
 `pvSigBlob`  
 [in]指向二进制 COM + 方法的签名的指针。  
  
 `cbSibBlob`  
 [in]大小，以字节为单位的`pvSigBlob`。  
  
 `pmi`  
 [out]指向方法的元数据签名定义的标记。  
  
## <a name="requirements"></a>要求  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** Cor.h  
  
 **库：**用作 MsCorEE.dll 中的资源  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>另请参阅  
 [IMetaDataEmit2 接口](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)  
 [IMetaDataEmit 接口](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
