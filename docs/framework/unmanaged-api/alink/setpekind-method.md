---
title: SetPEKind 方法
ms.date: 03/30/2017
api_name:
- IALink2.SetPEKind
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- SetPEKind
helpviewer_keywords:
- SetPEKind method
ms.assetid: 050e77ee-3014-45c0-9e29-2ebe29347b0d
topic_type:
- apiref
ms.openlocfilehash: 5a8442b1f0869e1592a05dfeeb0f5e6d583f3ea8
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79179388"
---
# <a name="setpekind-method"></a>SetPEKind 方法
确定可移植可执行类型，无论是特定于机器还是与机器无关。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT SetPEKind(  
    mdAssembly AssemblyID,  
    mdToken FileToken,  
    DWORD dwPEKind,  
    DWORD dwMachine  
) PURE;
```  
  
## <a name="parameters"></a>parameters  
 `AssemblyID`  
 程序集的 ID。  
  
 `FileToken`  
 要为其设置 PE 类型的文件令牌。 如果未`AssemblyID`指示未绑定网络模块，则可以为 NULL。  
  
 `dwPEKind`  
 PE 的类型，如[CorPEKind 枚举](../metadata/corpekind-enumeration.md)所示。  
  
 `dwMachine`  
 目标计算机体系结构，如 NT 标头中所示。  
  
## <a name="return-value"></a>返回值  
 如果方法成功，则返回S_OK。  
  
## <a name="requirements"></a>要求  
 需要 alink.h.  
  
## <a name="see-also"></a>另请参阅

- [GetPEKind 方法](../metadata/imetadataimport2-getpekind-method.md)
- [IALink2 接口](ialink2-interface.md)
- [IALink 接口](ialink-interface.md)
- [ALink API](index.md)
