---
title: "IMetaDataAssemblyEmit::DefineAssembly 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataAssemblyEmit.DefineAssembly
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataAssemblyEmit::DefineAssembly
helpviewer_keywords:
- IMetaDataAssemblyEmit::DefineAssembly method [.NET Framework metadata]
- DefineAssembly method [.NET Framework metadata]
ms.assetid: a0637d66-74bf-4f2d-8137-9ff838bccece
topic_type: apiref
caps.latest.revision: "18"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 86002eb38d72ee628dbf54d0b5691f0816e6f996
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="imetadataassemblyemitdefineassembly-method"></a>IMetaDataAssemblyEmit::DefineAssembly 方法
创建`Assembly`结构指定的程序集包含的元数据，并返回关联的元数据标记。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT DefineAssembly (  
    [in]  void                 *pbPublicKey,  
    [in]  ULONG                cbPublicKey,  
    [in]  ULONG                uHashAlgId,  
    [in]  LPCWSTR              szName,   
    [in]  ASSEMBLYMETADATA     *pMetaData,  
    [in]  DWORD                dwAssemblyFlags,  
    [out] mdAssembly           *pmda  
);  
```  
  
#### <a name="parameters"></a>参数  
 `pbPublicKey`  
 [in]如果程序集没有强名称标识的程序集或为 NULL 的发布者公钥。  
  
 `cbPublicKey`  
 [in]以字节为单位的大小`pbPublicKey`。  
  
 `uHashAlgId`  
 [in]要使用加密文件中的程序集或为 NULL，以指定 sha-1 算法的哈希算法标识符。  
  
 `szName`  
 [in]程序集的用户可读文本名称。 此值不得超过 1024年个字符。  
  
 `pMetaData`  
 [in]指向包含程序集的版本、 平台和区域设置信息的 ASSEMBLYMETADATA 实例的指针。  
  
 `dwAssemblyFlags`  
 [in]组合[CorAssemblyFlags](../../../../docs/framework/unmanaged-api/metadata/corassemblyflags-enumeration.md)值，用于描述程序集的功能。  
  
 `pmda`  
 [out]指向元数据标记的指针。  
  
## <a name="remarks"></a>备注  
 只有一个`Assembly`元数据结构可定义一个清单内。  
  
## <a name="requirements"></a>要求  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** Cor.h  
  
 **库：**作为 MsCorEE.dll 中的资源  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>另请参阅  
 [IMetaDataAssemblyEmit 接口](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
