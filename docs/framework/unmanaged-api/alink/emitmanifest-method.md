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
ms.openlocfilehash: 9217a045a8ddf6ad41adcc71a9568a05fe3fb334
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54565535"
---
# <a name="emitmanifest-method"></a>EmitManifest 方法
发出最终清单。 导入的所有其他文件和设置所有选项之后调用此方法。 请勿对未绑定模块调用此方法。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT EmitManifest(  
    mdAssembly   AssemblyID,  
    DWORD*       pdwReserveSize,  
    mdAssembly*  ptkManifest  
) PURE;  
```  
  
#### <a name="parameters"></a>参数  
 `AssemblyID`  
 程序集的 ID。  
  
 `pdwReserveSize`  
 接收要保留在程序集文件中，从检索到的大小[StrongNameSignatureSize 函数](../../../../docs/framework/unmanaged-api/strong-naming/strongnamesignaturesize-function.md)。  
  
 `ptkManifest`  
 可选择性地接收的程序集清单标记。  
  
## <a name="return-value"></a>返回值  
 如果该方法成功，返回，则为 S_OK。  
  
## <a name="requirements"></a>要求  
 需要 alink.h。  
  
## <a name="see-also"></a>请参阅
- [IALink 接口](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [IALink2 接口](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [ALink API](../../../../docs/framework/unmanaged-api/alink/index.md)
