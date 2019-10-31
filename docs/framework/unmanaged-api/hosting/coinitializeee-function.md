---
title: CoInitializeEE 函数
ms.date: 03/30/2017
api_name:
- CoInitializeEE
api_location:
- mscoree.dll
- mscorsvr.dll
api_type:
- DLLExport
f1_keywords:
- CoInitializeEE
helpviewer_keywords:
- CoInitializeEE function [.NET Framework hosting]
ms.assetid: 7e42a928-5068-4ba6-b8c3-806551a01fa8
topic_type:
- apiref
ms.openlocfilehash: 9e90772ae8c3e6be5744fcccc9901123df871831
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73131945"
---
# <a name="coinitializeee-function"></a>CoInitializeEE 函数
确保将公共语言运行时执行引擎加载到进程中。 此函数在 .NET Framework 4 中已弃用。 改为使用[ICLRRuntimeHost：： Start](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-start-method.md)方法。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT CoInitializeEE (  
   [in] DWORD fFlags  
);  
```  
  
## <a name="parameters"></a>参数  
 `fFlags`  
 中[COINITIEE](../../../../docs/framework/unmanaged-api/metadata/coinitiee-enumeration.md)枚举常量之一。  
  
## <a name="return-value"></a>返回值  
 此方法返回 Winerror.h 中定义的标准 COM 错误代码，以及下表中的值。  
  
|返回代码|描述|  
|-----------------|-----------------|  
|S_OK|已成功加载执行引擎。|  
|S_FALSE|已经加载了执行引擎。|  
|E_FAIL|未能加载执行引擎。|  
  
## <a name="remarks"></a>备注  
 此方法加载尚未加载的执行引擎。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** Cor  
  
 **库：** 作为资源包括在 Mscoree.dll 中  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>请参阅

- [元数据全局静态函数](../../../../docs/framework/unmanaged-api/metadata/metadata-global-static-functions.md)
