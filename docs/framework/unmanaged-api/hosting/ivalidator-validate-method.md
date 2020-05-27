---
title: IValidator::Validate 方法
ms.date: 03/30/2017
api_name:
- IValidator.Validate
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- Validate
helpviewer_keywords:
- IValidator::Validate method [.NET Framework hosting]
- Validate method, IValidator interface [.NET Framework hosting]
ms.assetid: 7d68666a-fb73-4455-bebd-908d49a16abc
topic_type:
- apiref
ms.openlocfilehash: 688abd210cca193bf03c40f000b74ecb66eb8ede
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/27/2020
ms.locfileid: "84008542"
---
# <a name="ivalidatorvalidate-method"></a>IValidator::Validate 方法
验证指定的可移植可执行（PE）或 Microsoft 中间语言（MSIL）文件。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT Validate (  
    [in] IVEHandler            *veh,  
    [in] IUnknown              *pAppDomain,  
    [in] unsigned long          ulFlags,  
    [in] unsigned long          ulMaxError,  
    [in] unsigned long          token,  
    [in] LPWSTR                 fileName,  
    [in, size_is(ulSize)] BYTE *pe,  
    [in] unsigned long          ulSize  
);  
```  
  
## <a name="parameters"></a>参数  
 `veh`  
 中指向 `IVEHandler` 处理验证错误的实例的指针。  
  
 `pAppDomain`  
 中一个指针，指向要在其中加载文件的应用程序域。  
  
 `ulFlags`  
 中[ValidatorFlags](validatorflags-enumeration.md)值的按位组合，指示应执行的验证。  
  
 `ulMaxError`  
 中在退出验证之前允许的最大错误数。  
  
 `token`  
 中不使用。  
  
 `fileName`  
 中一个字符串，指定要验证的文件的名称。  
  
 `pe`  
 中指向存储文件的内存缓冲区的指针。  
  
 `ulSize`  
 中要验证的文件的大小（以字节为单位）。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。  
  
 **标头：** IValidator，IValidator  
  
 **库：** 作为资源包括在 Mscoree.dll 中  
  
 **.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
