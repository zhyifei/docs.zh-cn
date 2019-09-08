---
title: EmitManifest 方法
ms.date: 03/30/2017
api_name:
- EmitManifest
- IALink.EmitManifest
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- EmitManifest
helpviewer_keywords:
- EmitManifest method
ms.assetid: fdebc1f3-b62e-4d9e-b775-8ccaa8ecb250
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: bdab1fd10be8fd245f4348798232964721b4487a
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2019
ms.locfileid: "70777337"
---
# <a name="emitmanifest-method"></a>EmitManifest 方法
发出最终清单。 导入所有其他文件并设置所有选项后，调用此方法。 不要对未绑定的模块调用此方法。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT EmitManifest(  
    mdAssembly   AssemblyID,  
    DWORD*       pdwReserveSize,  
    mdAssembly*  ptkManifest  
) PURE;  
```  
  
## <a name="parameters"></a>参数  
 `AssemblyID`  
 程序集的 ID。  
  
 `pdwReserveSize`  
 接收程序集文件中要保留的大小，从[StrongNameSignatureSize 函数](../strong-naming/strongnamesignaturesize-function.md)检索。  
  
 `ptkManifest`  
 可以选择接收程序集清单标记。  
  
## <a name="return-value"></a>返回值  
 如果该方法成功，则返回 S_OK。  
  
## <a name="requirements"></a>要求  
 需要 alink。  
  
## <a name="see-also"></a>请参阅

- [IALink 接口](ialink-interface.md)
- [IALink2 接口](ialink2-interface.md)
- [ALink API](index.md)
