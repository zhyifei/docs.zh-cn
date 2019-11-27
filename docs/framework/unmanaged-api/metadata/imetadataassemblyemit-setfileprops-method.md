---
title: IMetaDataAssemblyEmit::SetFileProps 方法
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyEmit.SetFileProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyEmit::SetFileProps
helpviewer_keywords:
- IMetaDataAssemblyEmit::SetFileProps method [.NET Framework metadata]
- SetFileProps method [.NET Framework metadata]
ms.assetid: 85667d38-611c-45a9-938d-930ac7a7b681
topic_type:
- apiref
ms.openlocfilehash: 106ffeee521f69a73628b1fb6a611abc733583f9
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74431873"
---
# <a name="imetadataassemblyemitsetfileprops-method"></a>IMetaDataAssemblyEmit::SetFileProps 方法
修改指定的 `File` 元数据结构。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT SetFileProps (  
    [in] mdFile        file,  
    [in] const void    *pbHashValue,   
    [in] ULONG         cbHashValue,  
    [in] DWORD         dwFileFlags  
);  
```  
  
## <a name="parameters"></a>参数  
 `file`  
 中用于指定要修改的 `File` 元数据结构的元数据标记。  
  
 `pbHashValue`  
 中指向与该文件关联的哈希数据的指针。  
  
 `cbHashValue`  
 中`pbHashValue`的大小（以字节为单位）。  
  
 `dwFileFlags`  
 中[CorFileFlags](../../../../docs/framework/unmanaged-api/metadata/corfileflags-enumeration.md)值的按位组合，用于指定文件的各种属性。  
  
## <a name="remarks"></a>备注  
 若要创建 `File` 元数据结构，请使用[IMetaDataAssemblyEmit：:D efinefile](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-definefile-method.md)方法。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** Cor  
  
 **库：** 用作 Mscoree.dll 中的资源  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>另请参阅

- [IMetaDataAssemblyEmit 接口](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
