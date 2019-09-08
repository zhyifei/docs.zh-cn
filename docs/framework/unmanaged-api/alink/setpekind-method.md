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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 9a48dbd38d357b668c2794ae6305ceb9cad3dcf4
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2019
ms.locfileid: "70787196"
---
# <a name="setpekind-method"></a>SetPEKind 方法
确定可移植的可执行文件类型（特定于计算机或计算机不可知）。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT SetPEKind(  
    mdAssembly AssemblyID,  
    mdToken FileToken,  
    DWORD dwPEKind,  
    DWORD dwMachine  
) PURE;   
```  
  
## <a name="parameters"></a>参数  
 `AssemblyID`  
 程序集的 ID。  
  
 `FileToken`  
 要为其设置 PE 类型的文件的标记。 如果不指示未`AssemblyID`绑定的 .netmodule，则可以为 NULL。  
  
 `dwPEKind`  
 PE 的类型，如[CorPEKind 枚举](../metadata/corpekind-enumeration.md)所示。  
  
 `dwMachine`  
 目标计算机体系结构，如 NT 标头中所示。  
  
## <a name="return-value"></a>返回值  
 如果该方法成功，则返回 S_OK。  
  
## <a name="requirements"></a>要求  
 需要 alink。  
  
## <a name="see-also"></a>请参阅

- [GetPEKind 方法](../metadata/imetadataimport2-getpekind-method.md)
- [IALink2 接口](ialink2-interface.md)
- [IALink 接口](ialink-interface.md)
- [ALink API](index.md)
