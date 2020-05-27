---
title: IMetaDataAssemblyEmit::DefineAssemblyRef 方法
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyEmit.DefineAssemblyRef
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyEmit::DefineAssemblyRef
helpviewer_keywords:
- DefineAssemblyRef method [.NET Framework metadata]
- IMetaDataAssemblyEmit::DefineAssemblyRef method [.NET Framework metadata]
ms.assetid: 0b284b18-0084-4b3a-912a-5ebe9f29c88b
topic_type:
- apiref
ms.openlocfilehash: 612463bca18c23fac0b086adde2d208a0fbc5ae5
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/27/2020
ms.locfileid: "84008163"
---
# <a name="imetadataassemblyemitdefineassemblyref-method"></a>IMetaDataAssemblyEmit::DefineAssemblyRef 方法
创建包含此程序集引用的程序集的元数据的 `AssemblyRef` 结构，并返回关联的元数据标记。  
  
## <a name="syntax"></a>语法  
  
```cpp  
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
  
## <a name="parameters"></a>参数  
 `pbPublicKeyOrToken`  
 中所引用程序集的发行者的公钥。 Helper 函数[StrongNameTokenFromAssembly](../strong-naming/strongnametokenfromassembly-function.md)可用于获取公钥哈希作为此参数传递。  
  
 `cbPublicKeyOrToken`  
 中的大小（以字节为单位） `pbPublicKeyOrToken` 。  
  
 `szName`  
 中程序集的用户可读文本名称。 此值不能超过1024个字符。  
  
 `pMetaData`  
 中一个 ASSEMBLYMETADATA 实例，其中包含所引用程序集的版本、平台和区域设置信息。  
  
 `pbHashValue`  
 中与所引用的程序集关联的哈希数据。 可选。  
  
 `cbHashValue`  
 中的大小（以字节为单位） `pbHashValue` 。  
  
 `dwAssemblyRefFlags`  
 中影响执行引擎行为的[CorAssemblyFlags](corassemblyflags-enumeration.md)值的按位组合。  
  
 `pmdar`  
 弄指向返回的 `AssemblyRef` 元数据标记的指针。  
  
## <a name="remarks"></a>备注  
 `AssemblyRef`必须为此程序集引用的每个程序集定义一个元数据结构。  
  
 在运行时，被引用程序集的详细信息将传递给程序集解析程序，并指示它们表示 "生成的" 信息。 然后，程序集冲突解决程序将应用策略。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。  
  
 **标头：** Cor  
  
 **库：** 用作 Mscoree.dll 中的资源  
  
 **.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>另请参阅

- [IMetaDataAssemblyEmit 接口](imetadataassemblyemit-interface.md)
