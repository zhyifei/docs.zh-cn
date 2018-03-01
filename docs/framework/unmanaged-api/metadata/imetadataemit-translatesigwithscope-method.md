---
title: "IMetaDataEmit::TranslateSigWithScope 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- IMetaDataEmit.TranslateSigWithScope
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::TranslateSigWithScope
helpviewer_keywords:
- TranslateSigWithScope method [.NET Framework metadata]
- IMetaDataEmit::TranslateSigWithScope method [.NET Framework metadata]
ms.assetid: 47915d33-b7bf-409e-b484-4ee1df15de22
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: ceb6a8bfbee5823e7080d8c98647da93a10a5b79
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataemittranslatesigwithscope-method"></a>IMetaDataEmit::TranslateSigWithScope 方法
将程序集导入当前作用域和为合并的作用域中获取新的元数据签名。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT TranslateSigWithScope (   
    [in]  IMetaDataAssemblyImport   *pAssemImport,   
    [in]  const void                *pbHashValue,   
    [in]  ULONG                     cbHashValue,   
    [in]  IMetaDataImport           *import,   
    [in]  PCCOR_SIGNATURE           pbSigBlob,   
    [in]  ULONG                     cbSigBlob,  
    [in]  IMetaDataAssemblyEmit     *pAssemEmit,   
    [in]  IMetaDataEmit             *emit,   
    [out] PCOR_SIGNATURE            pvTranslatedSig,   
    [in]  ULONG                     cbTranslatedSigMax,   
    [out] ULONG                     *pcbTranslatedSig   
);  
```  
  
#### <a name="parameters"></a>参数  
 `pAssemImport`  
 [in]用于导入程序集 （其中定义签名） 的接口。  
  
 `pbHashValue`  
 [in]程序集哈希 blob。  
  
 `cbHashValue`  
 [in]中的字节计数`pbHashValue`。  
  
 `import`  
 [in]用于导入元数据范围的接口。  
  
 `pbSigBlob`  
 [in]要导入的签名。  
  
 `cbSigBlob`  
 [in]大小，以字节为单位的`pbSigBlob`。  
  
 `pAssemEmit`  
 [in]用于导出程序集的接口。  
  
 `emit`  
 [in]用于导出元数据范围的接口。  
  
 `pvTranslatedSig`  
 [out]要保存已翻译的签名 blob 的缓冲区。  
  
 `cbTranslatedSigMax`  
 [in]容量，以字节为单位的`pvTranslatedSig`。  
  
 `pcbTranslatedSig`  
 [out]已翻译的签名中的实际字节数。  
  
## <a name="requirements"></a>惠?  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** Cor.h  
  
 **库：**用作 MSCorEE.dll 中的资源  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>请参阅  
 [IMetaDataAssemblyEmit 接口](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)  
 [IMetaDataAssemblyImport 接口](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)  
 [IMetaDataEmit Interface](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [IMetaDataEmit2 Interface](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)  
 [IMetaDataImport 接口](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
