---
title: StrongNameGetBlob 函数
ms.date: 03/30/2017
api_name:
- StrongNameGetBlob
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameGetBlob
helpviewer_keywords:
- StrongNameGetBlob function [.NET Framework strong naming]
ms.assetid: 15d09166-be00-4696-913f-2c1fbc7ac2e1
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a465b38951593fea7f36ef4ffba32e282f079f77
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54533593"
---
# <a name="strongnamegetblob-function"></a>StrongNameGetBlob 函数
使用指定地址处可执行文件的二进制表示形式填充指定的缓冲区。  
  
 此函数已弃用。 使用[iclrstrongname:: Strongnamegetblob](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetblob-method.md)方法相反。  
  
## <a name="syntax"></a>语法  
  
```  
BOOLEAN StrongNameGetBlob (  
    [in]  LPCWSTR    wszFilePath,  
    [in]  BYTE       *pbBlob,  
    [in, out] DWORD  *pcbBlob  
);  
```  
  
#### <a name="parameters"></a>参数  
 `wszFilePath`  
 [in]要加载的可执行文件是有效路径。  
  
 `pbBlob`  
 [in]若要加载的可执行文件读入的缓冲区。  
  
 `pcbBlob`  
 [in、 out]请求的最大大小，以字节为单位， `pbBlob`。 在返回时，实际大小，以字节为单位的`pbBlob`。  
  
## <a name="return-value"></a>返回值  
 `true` 在成功完成;否则为`false`。  
  
## <a name="remarks"></a>备注  
 如果`StrongNameGetBlob`函数不成功完成，则调用[StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md)函数检索最后一个生成的错误。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** StrongName.h  
  
 **库：** 包含为 MsCorEE.dll 中的资源  
  
 **.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>请参阅
- [StrongNameGetBlob 方法](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetblob-method.md)
- [StrongNameGetBlobFromImage 方法](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetblobfromimage-method.md)
- [ICLRStrongName 接口](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
