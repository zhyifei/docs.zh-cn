---
title: "IMetaDataAssemblyEmit::DefineFile 方法"
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
- IMetaDataAssemblyEmit.DefineFile
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyEmit::DefineFile
helpviewer_keywords:
- IMetaDataAssemblyEmit::DefineFile method [.NET Framework metadata]
- DefineFile method [.NET Framework metadata]
ms.assetid: c065aadf-c1ca-4981-bde6-597042cb29c4
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 48584822d7a2f31c466401db3a24156a71ad7011
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataassemblyemitdefinefile-method"></a>IMetaDataAssemblyEmit::DefineFile 方法
创建包含此程序集引用的程序集的元数据的 `File` 元数据结构，并返回关联的元数据标记。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT DefineFile (  
    [in]  LPCWSTR        szName,   
    [in]  const void     *pbHashValue,   
    [in]  ULONG          cbHashValue,  
    [in]  DWORD          dwFileFlags,  
    [out] mdFile         *pmdf  
);  
```  
  
#### <a name="parameters"></a>参数  
 `szName`  
 [in]要使用的文件的名称。  
  
 `pbHashValue`  
 [in]指向与程序集关联的哈希数据的指针。  
  
 `cbHashValue`  
 [in]以字节为单位的大小`pbHashValue`。  
  
 `dwFileFlags`  
 [in]按位组合`FileFlags`指定属性设置的值。  
  
 `pmdf`  
 [out]指向返回的指针`File`令牌。  
  
## <a name="remarks"></a>备注  
 一个`File`必须为每个文件的已生成此程序集，不包括包含的元数据的文件时此程序集的一部分定义元数据结构。  
  
## <a name="requirements"></a>惠?  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** Cor.h  
  
 **库：**用作 MsCorEE.dll 中的资源  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>请参阅  
 [IMetaDataAssemblyEmit 接口](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
