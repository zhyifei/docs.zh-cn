---
title: "IMetaDataAssemblyEmit::SetAssemblyProps 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataAssemblyEmit.SetAssemblyProps
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataAssemblyEmit::SetAssemblyProps
helpviewer_keywords:
- SetAssemblyProps method [.NET Framework metadata]
- IMetaDataAssemblyEmit::SetAssemblyProps method [.NET Framework metadata]
ms.assetid: 91b633d7-9e75-43c3-a8d2-2144984e5f9e
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: d2c9336855d706a9861d4e832e5f0234cdf04db7
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="imetadataassemblyemitsetassemblyprops-method"></a>IMetaDataAssemblyEmit::SetAssemblyProps 方法
修改指定的 `Assembly` 元数据结构。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT SetAssemblyProps (  
    [in] mdAssembly               pma,  
    [in] const void               *pbPublicKey,  
    [in] ULONG                    cbPublicKey,  
    [in] ULONG                    ulHashAlgId,  
    [in] LPCWSTR                  szName,  
    [in] const ASSEMBLYMETADATA   *pMetaData,  
    [in] DWORD                    dwAssemblyFlags  
);  
```  
  
#### <a name="parameters"></a>参数  
 `pma`  
 [in]指定的元数据标记`Assembly`要修改的元数据结构。  
  
 `pbPublicKey`  
 [in]指向程序集的发布者的公钥的指针。  
  
 `cbPublicKey`  
 [in]以字节为单位的大小`pbPublicKey`。  
  
 `ulHashAlgId`  
 [in]用于哈希的程序集文件的哈希算法标识符。  
  
 `szName`  
 [in]程序集的用户可读文本名称。  
  
 `pMetaData`  
 [in]指向包含程序集的版本、 平台和区域设置信息 ASSEMBLYMETADATA 的指针。  
  
 `dwAssemblyFlags`  
 [in]按位组合[AssemblyFlags](../../../../docs/framework/unmanaged-api/metadata/assemblyflags-enumeration.md)指定的程序集的各种特性的值。  
  
## <a name="remarks"></a>备注  
 若要创建`Assembly`元数据结构，使用[imetadataassemblyemit:: Defineassembly](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineassembly-method.md)方法。  
  
## <a name="requirements"></a>要求  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** Cor.h  
  
 **库：**用作 MsCorEE.dll 中的资源  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>另请参阅  
 [IMetaDataAssemblyEmit 接口](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
