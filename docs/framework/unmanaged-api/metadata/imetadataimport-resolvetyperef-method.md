---
title: "IMetaDataImport::ResolveTypeRef 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataImport.ResolveTypeRef
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataImport::ResolveTypeRef
helpviewer_keywords:
- ResolveTypeRef method [.NET Framework metadata]
- IMetaDataImport::ResolveTypeRef method [.NET Framework metadata]
ms.assetid: 556bccfb-61bc-4761-b1d5-de4b1c18a38f
topic_type: apiref
caps.latest.revision: "15"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 64a783297b27c9d1400670eecb7dfe4cb69c2b96
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataimportresolvetyperef-method"></a>IMetaDataImport::ResolveTypeRef 方法
解析<xref:System.Type>指定的 TypeRef 标记所表示的引用。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT ResolveTypeRef (  
   [in]  mdTypeRef       tr,  
   [in]  REFIID          riid,  
   [out] IUnknown        **ppIScope,  
   [out] mdTypeDef       *ptd  
);  
```  
  
#### <a name="parameters"></a>参数  
 `tr`  
 [in]要返回的引用的类型信息的 TypeRef 元数据标记。  
  
 `riid`  
 [in]接口的 IID，以返回`ppIScope`。 通常，这是 IID_IMetaDataImport。  
  
 `ppIScope`  
 [out]一个指向在其中定义引用的类型的模块作用域接口。  
  
 `ptd`  
 [out]指向表示引用的类型的 TypeDef 标记的指针。  
  
## <a name="remarks"></a>备注  
  
> [!IMPORTANT]
>  如果加载多个应用程序域，则不要使用此方法。 该方法不遵从应用程序域边界。 如果已加载的程序集的多个版本，并且它们包含具有相同的命名空间的相同类型，该方法将返回它找到的第一个类型的模块作用域。  
  
 `ResolveTypeRef`方法搜索其他模块中的类型定义。 如果找到的类型定义，则`ResolveTypeRef`返回一个指向该模块作用域，以及该类型的 TypeDef 标记接口。  
  
 如果要将解析的类型引用具有 AssemblyRef，解析范围`ResolveTypeRef`方法搜索仅中已经打开与调用的元数据作用域的匹配项[imetadatadispenser:: Openscope](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscope-method.md)方法或[imetadatadispenser:: Openscopeonmemory](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscopeonmemory-method.md)方法。 这是因为`ResolveTypeRef`无法确定从仅在磁盘上或在全局程序集缓存中程序集的存储位置的 AssemblyRef 作用域。  
  
## <a name="requirements"></a>惠?  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** Cor.h  
  
 **库：**作为 MsCorEE.dll 中的资源  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>请参阅  
 [IMetaDataImport 接口](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [IMetaDataImport2 接口](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
