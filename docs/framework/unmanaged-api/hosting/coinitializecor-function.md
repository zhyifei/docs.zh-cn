---
title: CoInitializeCor 函数
ms.date: 03/30/2017
api_name:
- CoInitializeCor
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- CoInitializeCor
helpviewer_keywords:
- CoInitializeCor function [.NET Framework hosting]
ms.assetid: 9b9079fb-579e-4141-b3f0-791072dd40dc
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 438f2f58a4ce61d1757238fc46674611e4d677dc
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54508530"
---
# <a name="coinitializecor-function"></a>CoInitializeCor 函数
`CoInitializeCor` 已过时。  
  
## <a name="syntax"></a>语法  
  
```  
STDAPI CoInitializeCor (  
    DWORD fFlags  
);  
```  
  
## <a name="remarks"></a>备注  
 若要初始化公共语言运行时，使用[CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md)或[CorBindToCurrentRuntime](../../../../docs/framework/unmanaged-api/hosting/corbindtocurrentruntime-function.md)。  
  
## <a name="requirements"></a>要求  
 **标头：** Cor.h  
  
## <a name="see-also"></a>请参阅
- [元数据全局静态函数](../../../../docs/framework/unmanaged-api/metadata/metadata-global-static-functions.md)
