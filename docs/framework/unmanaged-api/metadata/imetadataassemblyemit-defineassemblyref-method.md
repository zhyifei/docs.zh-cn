---
title: "IMetaDataAssemblyEmit::DefineAssemblyRef 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataAssemblyEmit.DefineAssemblyRef
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataAssemblyEmit::DefineAssemblyRef
helpviewer_keywords:
- DefineAssemblyRef method [.NET Framework metadata]
- IMetaDataAssemblyEmit::DefineAssemblyRef method [.NET Framework metadata]
ms.assetid: 0b284b18-0084-4b3a-912a-5ebe9f29c88b
topic_type: apiref
caps.latest.revision: "17"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 123bd37d189477eade72e3b0e74f923fecce57a7
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataassemblyemitdefineassemblyref-method"></a>IMetaDataAssemblyEmit::DefineAssemblyRef 方法
创建包含此程序集引用的程序集的元数据的 `AssemblyRef` 结构，并返回关联的元数据标记。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT DefineAssemblyRef (  
    [in]  void                *pbPublicKeyOrToken,  
    [in]  ULONG               cbPublicKeyOrToken,  
    [in]  LPCWSTR             szName,  
    [in]  ASSEMBLYMETADATA    pMetaData,  
    [in]  void                *pbHashValue,  
    [in]  ULONG               cbHashValue,  
    [in]  DWORD               dwAssemblyRefFlags,  
    [out] mdAssemblyRef       *pmdar  
);  
```  
  
#### <a name="parameters"></a>参数  
 `pbPublicKeyOrToken`  
 [in]引用的程序集的发布者的公钥。 Helper 函数[StrongNameTokenFromAssembly](../../../../docs/framework/unmanaged-api/strong-naming/strongnametokenfromassembly-function.md)可以用于获取作为此参数进行传递的公钥的哈希。  
  
 `cbPublicKeyOrToken`  
 [in]以字节为单位的大小`pbPublicKeyOrToken`。  
  
 `szName`  
 [in]程序集的用户可读文本名称。 此值不得超过 1024年个字符。  
  
 `pMetaData`  
 [in]ASSEMBLYMETADATA 实例包含引用的程序集的版本、 平台和区域设置信息。  
  
 `pbHashValue`  
 [in]与引用的程序集关联的哈希数据。 可选。  
  
 `cbHashValue`  
 [in]以字节为单位的大小`pbHashValue`。  
  
 `dwAssemblyRefFlags`  
 [in]按位组合[CorAssemblyFlags](../../../../docs/framework/unmanaged-api/metadata/corassemblyflags-enumeration.md)影响执行引擎的行为的值。  
  
 `pmdar`  
 [out]指向返回的指针`AssemblyRef`元数据标记。  
  
## <a name="remarks"></a>备注  
 一个`AssemblyRef`必须为此程序集引用每个程序集定义元数据结构。  
  
 在运行时，引用的程序集的详细信息传递给它们表示"按生成"信息指示此程序集冲突解决程序。 此程序集冲突解决程序然后将应用策略。  
  
## <a name="requirements"></a>惠?  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** Cor.h  
  
 **库：**用作 MsCorEE.dll 中的资源  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>请参阅  
 [IMetaDataAssemblyEmit 接口](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
