---
title: "IMetaDataEmit::SetPermissionSetProps 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataEmit.SetPermissionSetProps
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataEmit::SetPermissionSetProps
helpviewer_keywords:
- SetPermissionSetProps method [.NET Framework metadata]
- IMetaDataEmit::SetPermissionSetProps method [.NET Framework metadata]
ms.assetid: 8eaee971-40bf-45e2-a3d8-6e57674213b6
topic_type: apiref
caps.latest.revision: "10"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 34f2357de8d7ec522b4d10212eb82e351df8d152
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataemitsetpermissionsetprops-method"></a>IMetaDataEmit::SetPermissionSetProps 方法
设置或更新功能之前调用定义的权限集的元数据签名[imetadataemit:: Definepermissionset](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definepermissionset-method.md)。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT SetPermissionSetProps (   
    [in]  mdToken         tk,   
    [in]  DWORD           dwAction,   
    [in]  void const      *pvPermission,   
    [in]  ULONG           cbPermission,   
    [out] mdPermission    *ppm   
);  
```  
  
#### <a name="parameters"></a>参数  
 `tk`  
 [in]表示要修饰的对象元数据标记。  
  
 `dwAction`  
 [in]A [CorDeclSecurity](../../../../docs/framework/unmanaged-api/metadata/cordeclsecurity-enumeration.md)值，该值指定要使用的声明性安全的类型。  
  
 `pvPermission`  
 [in]BLOB 的权限。  
  
 `cbPermission`  
 [in]大小，以字节为单位的`pvPermission`。  
  
 `ppm`  
 [out]`mdPermission`元数据标记表示更新的权限。  
  
## <a name="requirements"></a>惠?  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** Cor.h  
  
 **库：**用作 MSCorEE.dll 中的资源  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>请参阅  
 [IMetaDataEmit Interface](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [IMetaDataEmit2 Interface](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
