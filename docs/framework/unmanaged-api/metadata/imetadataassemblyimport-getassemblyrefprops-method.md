---
title: IMetaDataAssemblyImport::GetAssemblyRefProps 方法
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyImport.GetAssemblyRefProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyImport::GetAssemblyRefProps
helpviewer_keywords:
- IMetaDataAssemblyImport::GetAssemblyRefProps method [.NET Framework metadata]
- GetAssemblyRefProps method [.NET Framework metadata]
ms.assetid: 5c6b7fb4-cbca-4479-b650-ab9a99732ea0
topic_type:
- apiref
ms.openlocfilehash: 9aef471c1155070af0e9bcca14975a65bc5dc763
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175962"
---
# <a name="imetadataassemblyimportgetassemblyrefprops-method"></a>IMetaDataAssemblyImport::GetAssemblyRefProps 方法
使用指定的元数据签名获取程序集引用的属性集。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT GetAssemblyRefProps (  
    [in]  mdAssemblyRef        mdar,
    [out] const void          **ppbPublicKeyOrToken,
    [out] ULONG                *pcbPublicKeyOrToken,
    [out] LPWSTR               szName,
    [in]  ULONG                cchName,
    [out] ULONG                *pchName,
    [out] ASSEMBLYMETADATA     *pMetaData,
    [out] const void           **ppbHashValue,
    [out] ULONG                *pcbHashValue,
    [out] DWORD                *pdwAssemblyRefFlags  
);  
```  
  
## <a name="parameters"></a>parameters  
 `mdar`  
 [在]表示`mdAssemblyRef`要获取属性的程序集引用的元数据令牌。  
  
 `ppbPublicKeyOrToken`  
 [出]指向公钥或元数据令牌的指针。  
  
 `pcbPublicKeyOrToken`  
 [出]返回的公钥或令牌中的字节数。  
  
 `szName`  
 [出]程序集的简单名称。  
  
 `cchName`  
 [在]大字符的大小`szName`。  
  
 `pchName`  
 [出]指向 中实际返回的宽字符数的指针`szName`。  
  
 `pMetaData`  
 [出]指向包含程序集元数据的装配元数据结构的指针。  
  
 `ppbHashValue`  
 [出]指向哈希值的指针。 这是使用 SHA-1 算法引用的程序集`PublicKey`属性的哈希值，除非设置了[AssemblyRefFlags](../../../../docs/framework/unmanaged-api/metadata/assemblyrefflags-enumeration.md)枚举的 arfFullOriginator 标志。  
  
 `pcbHashValue`  
 [出]返回的哈希值中的宽字符数。  
  
 `pdwAssemblyRefFlags`  
 [出]指向用于描述应用于程序集的元数据的标志的指针。 标志值是一个或多个[CorAssemblyFlags](../../../../docs/framework/unmanaged-api/metadata/corassemblyflags-enumeration.md)值的组合。  
  
## <a name="return-value"></a>返回值  
 此方法如果成功，将返回S_OK;否则，它将返回 Winerror.h 标头文件中定义的错误代码之一。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标题：** 科尔赫  
  
 **库：** 用作 MsCorEE.dll 中的资源  
  
 **.NET 框架版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>另请参阅

- [IMetaDataAssemblyImport 接口](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
