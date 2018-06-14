---
title: ICorPublishAppDomain::GetName 方法
ms.date: 03/30/2017
api_name:
- ICorPublishAppDomain.GetName
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublishAppDomain::GetName
helpviewer_keywords:
- GetName method, ICorPublishAppDomain interface [.NET Framework debugging]
- ICorPublishAppDomain::GetName method [.NET Framework debugging]
ms.assetid: 6ef8ac9b-9803-4b65-8b13-25f3e0b1bc6b
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 796f8ea42cc5cbe13729f7b92e15bc214d62734d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33423853"
---
# <a name="icorpublishappdomaingetname-method"></a>ICorPublishAppDomain::GetName 方法
获取表示此应用程序域的名称[ICorPublishAppDomain](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomain-interface.md)。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT GetName (  
    [in]  ULONG32   cchName,   
    [out] ULONG32   *pcchName,  
    [out, size_is(cchName), length_is(*pcchName)]   
        WCHAR       *szName  
);  
```  
  
#### <a name="parameters"></a>参数  
 `cchName`  
 [in] `szName` 数组的大小。  
  
 `pcchName`  
 [out]指向的宽字符，包括 null 字符，在中返回数的指针`szName`数组。  
  
 `szName`  
 [out]在其中存储名称的数组。  
  
## <a name="remarks"></a>备注  
 如果`szName`为非 null`GetName`方法复制达`cchName`字符 （包括 null 终止符） 到`szName`。 如果非 null 返回在`pcchName`的实际名称 （包括 null 终止符） 中的字符数存储在`szName`数组。  
  
 `GetName`方法将返回而不考虑多少个字符已复制的则为 S_OK HRESULT。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** CorPub.idl、 CorPub.h  
  
 **库：** CorGuids.lib  
  
 **.NET framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>请参阅  
 [ICorPublishAppDomain 接口](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomain-interface.md)
