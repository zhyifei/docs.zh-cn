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
ms.openlocfilehash: 762c637696fdf79ccab6702918b5bf962ea55903
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178405"
---
# <a name="icorpublishappdomaingetname-method"></a>ICorPublishAppDomain::GetName 方法
获取此[ICorPublishAppDomain](icorpublishappdomain-interface.md)表示的应用程序域的名称。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT GetName (  
    [in]  ULONG32   cchName,
    [out] ULONG32   *pcchName,  
    [out, size_is(cchName), length_is(*pcchName)]
        WCHAR       *szName  
);  
```  
  
## <a name="parameters"></a>parameters  
 `cchName`  
 [in] `szName` 数组的大小。  
  
 `pcchName`  
 [出]数组中返回的指向宽字符数（包括空字符）的`szName`指针。  
  
 `szName`  
 [出]要在其中存储名称的数组。  
  
## <a name="remarks"></a>备注  
 如果`szName`为非空，`GetName`则该方法将最多复制到`cchName`字符（包括空终止符）到`szName`中。 如果在 中`pcchName`返回非 null，则名称中（包括空终止符）中的实际字符数存储在数组中`szName`。  
  
 无论`GetName`复制的字符数如何，该方法都会返回S_OK HRESULT。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标题：** 科尔普布.idl， 科尔普布.h  
  
 **库：** CorGuids.lib  
  
 **.NET 框架版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>另请参阅

- [ICorPublishAppDomain 接口](icorpublishappdomain-interface.md)
