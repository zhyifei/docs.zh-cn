---
title: StrongNameSignatureVerificationEx 函数
ms.date: 03/30/2017
api_name:
- StrongNameSignatureVerificationEx
api_location:
- mscoree.dll
- mscorwks.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameSignatureVerificationEx
helpviewer_keywords:
- StrongNameSignatureVerificationEx function [.NET Framework strong naming]
ms.assetid: cfe4b634-18bf-44b8-9773-d94fb7e8a480
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 08247c1ec5b868055e4836b3c0fb520a536374e8
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2019
ms.locfileid: "70798917"
---
# <a name="strongnamesignatureverificationex-function"></a>StrongNameSignatureVerificationEx 函数
获取一个值，该值指示提供的路径中的程序集清单是否包含强名称签名。  
  
 此函数已弃用。 改为使用[ICLRStrongName：： StrongNameSignatureVerificationEx](../hosting/iclrstrongname-strongnamesignatureverificationex-method.md)方法。  
  
## <a name="syntax"></a>语法  
  
```cpp  
BOOLEAN StrongNameSignatureVerificationEx (  
    [in]  LPCWSTR   wszFilePath,  
    [in]  BOOLEAN   fForceVerification,  
    [out] BOOLEAN   *pfWasVerified  
);  
```  
  
## <a name="parameters"></a>参数  
 `wszFilePath`  
 中要验证的程序集的可移植可执行文件（.exe 或 .dll）文件的路径。  
  
 `fForceVerification`  
 中如果需要重写注册表设置，则为; `false`否则为。 `true`  
  
 `pfWasVerified`  
 弄如果验证强名称签名， `false`则为; 否则为。 `true` `pfWasVerified`如果验证因为注册表`false`设置而成功，则也会设置为。  
  
## <a name="return-value"></a>返回值  
 `true`如果验证成功，则为;否则为`false`。  
  
## <a name="remarks"></a>备注  
 `StrongNameSignatureVerificationEx`提供与[StrongNameSignatureVerification](strongnamesignatureverification-function.md)函数相似的功能。 但是，的第二个输入参数和输出参数`StrongNameSignatureVerificationEx`的类型`BOOLEAN`为，而`DWORD`不是。  
  
## <a name="requirements"></a>要求  
 **适用**请参阅[系统需求](../../get-started/system-requirements.md)。  
  
 **标头：** Stackexchange.redis.strongname  
  
 **类库**作为资源包括在 mscoree.dll 中  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>请参阅

- [StrongNameSignatureVerificationEx 方法](../hosting/iclrstrongname-strongnamesignatureverificationex-method.md)
- [StrongNameSignatureVerification 方法](../hosting/iclrstrongname-strongnamesignatureverification-method.md)
- [ICLRStrongName 接口](../hosting/iclrstrongname-interface.md)
