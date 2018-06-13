---
title: IMetaDataAssemblyImport::GetAssemblyProps 方法
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyImport.GetAssemblyProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyImport::GetAssemblyProps
helpviewer_keywords:
- GetAssemblyProps method [.NET Framework metadata]
- IMetaDataAssemblyImport::GetAssemblyProps method [.NET Framework metadata]
ms.assetid: 0eaa4aa9-9441-444a-920c-e4b2a2db899e
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 911d0d1444e2cf3cb8241eeeff63a5a86b4ab806
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33446269"
---
# <a name="imetadataassemblyimportgetassemblyprops-method"></a>IMetaDataAssemblyImport::GetAssemblyProps 方法
获取具有指定的元数据签名的程序集的属性集。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT GetAssemblyProps (  
    [in]  mdAssembly          mda,  
    [out] const void          **ppbPublicKey,   
    [out] ULONG               *pcbPublicKey,  
    [out] ULONG               *pulHashAlgId,  
    [out] LPWSTR              szName,  
    [in] ULONG                cchName,  
    [out] ULONG               *pchName,  
    [out] ASSEMBLYMETADATA    *pMetaData,  
    [out] DWORD               *pdwAssemblyFlags  
);  
```  
  
#### <a name="parameters"></a>参数  
 `mda`  
 [in]。 `mdAssembly`表示要为其获取属性的程序集的元数据标记。  
  
 `ppbPublicKey`  
 [out]公钥或元数据标记的指针。  
  
 `pcbPublicKey`  
 [out]返回公钥中的字节数。  
  
 `pulHashAlgId`  
 [out]指向用于在程序集中的文件执行哈希算法的指针。  
  
 `szName`  
 [out]程序集的简单名称。  
  
 `cchName`  
 [in]大小，以宽字符为单位的`szName`。  
  
 `pchName`  
 [out]中实际返回的宽字符数`szName`。  
  
 `pMetaData`  
 [out]指向包含程序集元数据的 ASSEMBLYMETADATA 结构的指针。  
  
 `pdwAssemblyFlags`  
 [out]描述应用于程序集的元数据的标志。 此值是一个或多个组合[CorAssemblyFlags](../../../../docs/framework/unmanaged-api/metadata/corassemblyflags-enumeration.md)值。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** Cor.h  
  
 **库：** 用作 MsCorEE.dll 中的资源  
  
 **.NET framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>请参阅  
 [IMetaDataAssemblyImport 接口](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
