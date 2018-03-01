---
title: "SetManifestFile 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- IALink3.SetManifestFile
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- SetManifestFile
helpviewer_keywords:
- SetManifestFile method
ms.assetid: 1b33de4c-19cb-4a36-a93f-8675b2a36d58
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: cf48153454fbb2c24dc3f1cfe1f82deefa4ee723
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="setmanifestfile-method"></a>SetManifestFile 方法
使您能够指定或重置链接器使用在创建程序集时的清单文件。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT SetManifestFile(  
    LPCWSTR pszFile  
) PURE;  
```  
  
#### <a name="parameters"></a>参数  
 `pszFile`  
  
 其内容放入 Win32 资源 blob 清单文件的名称。  
  
## <a name="return-value"></a>返回值  
 如果该方法成功，则返回，则为 S_OK。  
  
## <a name="remarks"></a>备注  
 要求提供 Win32ResBlob 之前调用此操作。 值`pszFile`参数是清单文件被读取其内容并将其放在 RT_MANIFEST ID 的 Win32 资源的名称。 通过使用 NULL 的参数调用时，将清除任何以前读取的清单。 这使另一个用于链接器的状态重置为的初始化时。  
  
## <a name="requirements"></a>惠?  
 需要 aLink.h  
  
## <a name="see-also"></a>请参阅  
 [IALink3 接口](../../../../docs/framework/unmanaged-api/alink/ialink3-interface.md)  
 [ALink API](../../../../docs/framework/unmanaged-api/alink/index.md)  
 [IALink 接口](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [Al.exe（程序集链接器）](../../../../docs/framework/tools/al-exe-assembly-linker.md)
