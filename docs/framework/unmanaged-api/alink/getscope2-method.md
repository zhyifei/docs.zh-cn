---
title: GetScope2 方法
ms.date: 03/30/2017
api_name:
- IALink2.GetScope2
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- GetScope2
helpviewer_keywords:
- GetScope2 method
ms.assetid: 49435665-6f5a-4acd-9034-8c9244a04a63
topic_type:
- apiref
ms.openlocfilehash: 40df78cdf99c2e0f53be9664f3f5c6386b6c6f93
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79179399"
---
# <a name="getscope2-method"></a>GetScope2 方法
获取导入范围。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT GetScope2(  
    mdAssembly AssemblyID,  
    mdToken FileToken,  
    DWORD dwScope,  
    IMetaDataImport2** ppImportScope  
) PURE;
```  
  
## <a name="parameters"></a>parameters  
 `AssemblyID`  
 目标程序集的 ID。  
  
 `FileToken`  
 要从中导入的文件的 ID。  
  
 `dwScope`  
 要导入的零基作用域。  
  
 `ppImportScope`  
 接收指向[IMetaDataImport2 接口](../metadata/imetadataimport2-interface.md)的指针，用于指示的范围。  
  
## <a name="return-value"></a>返回值  
 如果方法成功，则返回S_OK。  
  
## <a name="requirements"></a>要求  
 需要 alink.h.  
  
## <a name="see-also"></a>另请参阅

- [IALink2 接口](ialink2-interface.md)
- [IALink 接口](ialink-interface.md)
- [ALink API](index.md)
