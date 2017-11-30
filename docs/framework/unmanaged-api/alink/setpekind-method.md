---
title: "SetPEKind 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IALink2.SetPEKind
api_location: alink.dll
api_type: COM
f1_keywords: SetPEKind
helpviewer_keywords: SetPEKind method
ms.assetid: 050e77ee-3014-45c0-9e29-2ebe29347b0d
topic_type: apiref
caps.latest.revision: "6"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: d511bcda2ab4e879c123d866b3f6c887173c1d2f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="setpekind-method"></a>SetPEKind 方法
确定特定于计算机或计算机不可知的可移植可执行文件类型。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT SetPEKind(  
    mdAssembly AssemblyID,  
    mdToken FileToken,  
    DWORD dwPEKind,  
    DWORD dwMachine  
) PURE;   
```  
  
#### <a name="parameters"></a>参数  
 `AssemblyID`  
 程序集的 ID。  
  
 `FileToken`  
 PE 类型要为其设置的文件的令牌。 如果可以为 NULL`AssemblyID`并不表示未绑定的程序集。  
  
 `dwPEKind`  
 PE，所述的一种[CorPEKind 枚举](../../../../docs/framework/unmanaged-api/metadata/corpekind-enumeration.md)。  
  
 `dwMachine`  
 目标计算机基础结构，如 NT 标头中所示。  
  
## <a name="return-value"></a>返回值  
 如果该方法成功，则返回，则为 S_OK。  
  
## <a name="requirements"></a>要求  
 需要 alink.h。  
  
## <a name="see-also"></a>另请参阅  
 [GetPEKind 方法](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-getpekind-method.md)  
 [IALink2 接口](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [IALink 接口](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [ALink API](../../../../docs/framework/unmanaged-api/alink/index.md)
