---
title: SetManifestFile 方法
ms.date: 03/30/2017
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
ms.openlocfilehash: df97f4c37d8f335ce183685debd7c0933be910ed
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74445560"
---
# <a name="setmanifestfile-method"></a>SetManifestFile 方法
使您能够在创建程序集时指定或重置链接器使用的清单文件。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT SetManifestFile(  
    LPCWSTR pszFile  
) PURE;  
```  
  
## <a name="parameters"></a>参数  
 `pszFile`  
  
 其内容将放入 Win32 资源 blob 中的清单文件的名称。  
  
## <a name="return-value"></a>返回值  
 如果方法成功，则返回 S_OK。  
  
## <a name="remarks"></a>备注  
 在请求 Win32ResBlob 之前调用此。 `pszFile` 参数的值是清单文件的名称，该清单文件的内容被读取并置于 Win32 资源中，并且 ID 为 RT_MANIFEST。 使用 NULL 的参数调用时，将清除任何以前的读取清单。 这样一来，就可以将链接器的状态重置为初始化时的状态。  
  
## <a name="requirements"></a>要求  
 需要 aLink  
  
## <a name="see-also"></a>另请参阅

- [IALink3 接口](ialink3-interface.md)
- [ALink API](index.md)
- [IALink 接口](ialink-interface.md)
- [Al.exe（程序集链接器）](../../tools/al-exe-assembly-linker.md)
