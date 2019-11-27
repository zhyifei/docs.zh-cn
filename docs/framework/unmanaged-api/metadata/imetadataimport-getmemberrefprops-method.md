---
title: IMetaDataImport::GetMemberRefProps 方法
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetMemberRefProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetMemberRefProps
helpviewer_keywords:
- GetMemberRefProps method [.NET Framework metadata]
- IMetaDataImport::GetMemberRefProps method [.NET Framework metadata]
ms.assetid: 0ea73055-ece0-4151-a094-414c88ef8941
topic_type:
- apiref
ms.openlocfilehash: 1d6d66ea62cbf679f722f830b3638455001aedd6
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74437486"
---
# <a name="imetadataimportgetmemberrefprops-method"></a>IMetaDataImport::GetMemberRefProps 方法
获取与指定标记引用的成员关联的元数据。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT GetMemberRefProps (  
   [in]  mdMemberRef       mr,   
   [out] mdToken           *ptk,   
   [out] LPWSTR            szMember,   
   [in]  ULONG             cchMember,   
   [out] ULONG             *pchMember,   
   [out] PCCOR_SIGNATURE   *ppvSigBlob,   
   [out] ULONG             *pbSig   
);  
```  
  
## <a name="parameters"></a>参数  
 `mr`  
 中要为其返回关联的元数据的 MemberRef 标记。  
  
 `ptk`  
 弄TypeDef 或 TypeRef 或 TypeSpec 标记，它表示声明成员的类，或表示声明成员的 module 类的 ModuleRef 标记或表示成员的 MethodDef。  
  
 `szMember`  
 弄成员名称的字符串缓冲区。  
  
 `cchMember`  
 中`szMember`中的请求大小（以宽字符为大小）。  
  
 `pchMember`  
 弄`szMember`的宽字符返回的大小。  
  
 `ppvSibBlob`  
 弄指向成员的二进制元数据签名的指针。  
  
 `pbSig`  
 弄`ppvSigBlob`的大小（以字节为单位）。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** Cor  
  
 **库：** 作为资源包括在 Mscoree.dll 中  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>另请参阅

- [IMetaDataImport 接口](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [IMetaDataImport2 接口](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
