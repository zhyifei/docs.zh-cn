---
title: IValidator::FormatEventInfo 方法
ms.date: 03/30/2017
api_name:
- IValidator.FormatEventInfo
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- FormatEventInfo
helpviewer_keywords:
- IValidator::FormatEventInfo method [.NET Framework hosting]
- FormatEventInfo method, IValidator interface [.NET Framework hosting]
ms.assetid: 4c0c7477-05ba-461b-b21b-cbfba95f1db1
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 875052ed26e83de50807e33e9c74dcf89f7ee679
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33440640"
---
# <a name="ivalidatorformateventinfo-method"></a>IValidator::FormatEventInfo 方法
获取对应于指定的验证错误的错误消息。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT FormatEventInfo(  
    [in] HRESULT            hVECode,  
    [in] VEContext          Context,  
    [in, out] LPWSTR        msg,  
    [in] unsigned long      ulMaxLength,  
    [in] SAFEARRAY(VARIANT) psa  
);  
```  
  
#### <a name="parameters"></a>参数  
 `hVECode`  
 [in]HRESULT 值传递到验证错误处理程序。  
  
 `Context`  
 [in]A`VEContext`实例，其中包含有关验证错误的上下文信息。  
  
 `msg`  
 [在中，out]包含返回的错误消息的字符串。  
  
 `ulMaxLength`  
 [in]错误消息的最大长度。  
  
 `psa`  
 [in]包含描述错误的其他参数的安全数组。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** IValidator.idl、 IValidator.h  
  
 **库：** 作为 MSCorEE.dll 中的资源  
  
 **.NET framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>请参阅  
 
