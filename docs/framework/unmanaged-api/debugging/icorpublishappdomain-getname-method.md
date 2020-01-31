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
ms.openlocfilehash: 4325d61d12a66b17f88e5e368cbbc7806d0a3ec5
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/28/2020
ms.locfileid: "76790706"
---
# <a name="icorpublishappdomaingetname-method"></a>ICorPublishAppDomain::GetName 方法
获取此[ICorPublishAppDomain](icorpublishappdomain-interface.md)所表示的应用程序域的名称。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT GetName (  
    [in]  ULONG32   cchName,   
    [out] ULONG32   *pcchName,  
    [out, size_is(cchName), length_is(*pcchName)]   
        WCHAR       *szName  
);  
```  
  
## <a name="parameters"></a>参数  
 `cchName`  
 [in] `szName` 数组的大小。  
  
 `pcchName`  
 弄一个指针，指向在 `szName` 数组中返回的宽字符数，包括 null 字符。  
  
 `szName`  
 弄要在其中存储名称的数组。  
  
## <a name="remarks"></a>备注  
 如果 `szName` 为非 null，则 `GetName` 方法会将最多 `cchName` 个字符（包括 null 结束符）复制到 `szName`中。 如果在 `pcchName`中返回非 null，则名称中的实际字符数（包括 null 终止符）将存储在 `szName` 数组中。  
  
 无论复制了多少个字符，`GetName` 方法都将返回一个 S_OK HRESULT。  
  
## <a name="requirements"></a>需求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** CorPub，CorPub  
  
 **库：** CorGuids.lib  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>另请参阅

- [ICorPublishAppDomain 接口](icorpublishappdomain-interface.md)
