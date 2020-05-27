---
title: IMetaDataEmit::TranslateSigWithScope 方法
ms.date: 03/30/2017
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
ms.openlocfilehash: 7ef6dbc46806febc6fba89b39a8b894377225c23
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/27/2020
ms.locfileid: "84003944"
---
# <a name="imetadataemittranslatesigwithscope-method"></a>IMetaDataEmit::TranslateSigWithScope 方法
将程序集导入到当前作用域中，并为合并的作用域获取新的元数据签名。  
  
## <a name="syntax"></a>语法  
  
```cpp  
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
  
## <a name="parameters"></a>参数  
 `pAssemImport`  
 中导入程序集的接口（在其中定义签名）。  
  
 `pbHashValue`  
 中程序集的哈希 blob。  
  
 `cbHashValue`  
 中中的字节数 `pbHashValue` 。  
  
 `import`  
 中导入元数据范围的接口。  
  
 `pbSigBlob`  
 中要导入的签名。  
  
 `cbSigBlob`  
 中的大小（以字节为单位） `pbSigBlob` 。  
  
 `pAssemEmit`  
 中导出程序集的接口。  
  
 `emit`  
 中导出元数据范围的接口。  
  
 `pvTranslatedSig`  
 弄用于保存已转换的签名 blob 的缓冲区。  
  
 `cbTranslatedSigMax`  
 中的容量（以字节为单位） `pvTranslatedSig` 。  
  
 `pcbTranslatedSig`  
 弄已翻译签名中的实际字节数。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。  
  
 **标头：** Cor  
  
 **库：** 用作 Mscoree.dll 中的资源  
  
 **.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>另请参阅

- [IMetaDataAssemblyEmit 接口](imetadataassemblyemit-interface.md)
- [IMetaDataAssemblyImport 接口](imetadataassemblyimport-interface.md)
- [IMetaDataEmit 接口](imetadataemit-interface.md)
- [IMetaDataEmit2 接口](imetadataemit2-interface.md)
- [IMetaDataImport 接口](imetadataimport-interface.md)
