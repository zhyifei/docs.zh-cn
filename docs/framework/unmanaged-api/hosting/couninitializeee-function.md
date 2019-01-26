---
title: CoUninitializeEE 函数
ms.date: 03/30/2017
api_name:
- CoUninitializeEE
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- CoUninitializeEE
helpviewer_keywords:
- CoUninitializeEE function [.NET Framework hosting]
ms.assetid: 5f5a311a-839a-465f-89d9-ff1c74da9736
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ef5faff6682ed6c043e81212f2cb27d4cfbd813d
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54601852"
---
# <a name="couninitializeee-function"></a>CoUninitializeEE 函数
`CoUninitializeEE` 已过时，不提供任何功能。  
  
## <a name="syntax"></a>语法  
  
```  
void CoUninitializeEE (  
    BOOL fFlags  
);  
```  
  
## <a name="remarks"></a>备注  
 公共语言运行时执行引擎不能从进程中卸载。 若要关闭的情况下执行引擎调用[CorExitProcess](../../../../docs/framework/unmanaged-api/hosting/corexitprocess-function.md)。  
  
## <a name="see-also"></a>请参阅
- [CoInitializeEE 函数](../../../../docs/framework/unmanaged-api/hosting/coinitializeee-function.md)
- [元数据全局静态函数](../../../../docs/framework/unmanaged-api/metadata/metadata-global-static-functions.md)
