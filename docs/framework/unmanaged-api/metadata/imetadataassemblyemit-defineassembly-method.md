---
title: IMetaDataAssemblyEmit::DefineAssembly 方法
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyEmit.DefineAssembly
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyEmit::DefineAssembly
helpviewer_keywords:
- IMetaDataAssemblyEmit::DefineAssembly method [.NET Framework metadata]
- DefineAssembly method [.NET Framework metadata]
ms.assetid: a0637d66-74bf-4f2d-8137-9ff838bccece
topic_type:
- apiref
ms.openlocfilehash: 14bd352099890e4ca36321d550b8e982d4373231
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177892"
---
# <a name="imetadataassemblyemitdefineassembly-method"></a>IMetaDataAssemblyEmit::DefineAssembly 方法
创建包含`Assembly`指定程序集元数据的结构并返回关联的元数据令牌。  
  
## <a name="syntax"></a>语法  
  
```cpp  
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
  
## <a name="parameters"></a>parameters  
 `pbPublicKey`  
 [在]标识程序集的发布者的公共密钥，如果程序集未强命名，则为 NULL。  
  
 `cbPublicKey`  
 [在]的大小（以字节为单位）。 `pbPublicKey`  
  
 `uHashAlgId`  
 [在]用于加密程序集中的文件的哈希算法的标识符，或用于指定 SHA-1 算法的 NULL。  
  
 `szName`  
 [在]程序集的人类可读文本名称。 此值不得超过 1024 个字符。  
  
 `pMetaData`  
 [在]指向 ASSEMBLYMETADATA 实例的指针，其中包含程序集的版本、平台和区域设置信息。  
  
 `dwAssemblyFlags`  
 [在]描述程序集功能的[CorAssemblyFlags](../../../../docs/framework/unmanaged-api/metadata/corassemblyflags-enumeration.md)值的组合。  
  
 `pmda`  
 [出]指向元数据令牌的指针。  
  
## <a name="remarks"></a>备注  
 只能在清单`Assembly`中定义一个元数据结构。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标题：** 科尔赫  
  
 **库：** 作为资源包含在 MsCorEE.dll 中  
  
 **.NET 框架版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>另请参阅

- [IMetaDataAssemblyEmit 接口](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
