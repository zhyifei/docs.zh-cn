---
title: GetHashFromHandle 函数
ms.date: 03/30/2017
api_name:
- GetHashFromHandle
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- GetHashFromHandle
helpviewer_keywords:
- GetHashFromHandle function [.NET Framework strong naming]
ms.assetid: 9e00337f-b307-4602-9bc3-965a8dbf02cd
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3eac353252f5a97402cbd883895b3e397c39edd6
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2019
ms.locfileid: "70799183"
---
# <a name="gethashfromhandle-function"></a>GetHashFromHandle 函数
使用指定的哈希算法，生成具有指定文件句柄的文件内容的哈希。  
  
 此函数已弃用。 改为使用[ICLRStrongName：： GetHashFromHandle](../hosting/iclrstrongname-gethashfromhandle-method.md)方法。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT GetHashFromHandle (  
    [in]  HANDLE   hFile,  
    [in, out] unsigned int   *piHashAlg,  
    [out] BYTE     *pbHash,  
    [in]  DWORD    cchHash,  
    [out] DWORD    *pchHash  
);  
```  
  
## <a name="parameters"></a>参数  
 `hFile`  
 中要进行哈希处理的文件的句柄。  
  
 `piHashAlg`  
 [in，out]指定哈希算法的常量。 对于默认算法，使用零。  
  
 `pbHash`  
 弄返回的哈希缓冲区。  
  
 `cchHash`  
 中请求的最大大小`pbHash`。  
  
 `pchHash`  
 弄返回`pbHash`的的大小（以字节为单位）。  
  
## <a name="requirements"></a>要求  
 **适用**请参阅[系统需求](../../get-started/system-requirements.md)。  
  
 **标头：** Stackexchange.redis.strongname  
  
 **类库**作为资源包括在 Mscoree.dll 中  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>请参阅

- [GetHashFromHandle 方法](../hosting/iclrstrongname-gethashfromhandle-method.md)
- [ICLRStrongName 接口](../hosting/iclrstrongname-interface.md)
