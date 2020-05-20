---
title: ICLRMetaHost::ExitProcess 方法
ms.date: 03/30/2017
api_name:
- ICLRMetaHost.ExitProcess
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRMetaHost::ExitProcess
helpviewer_keywords:
- ICLRMetaHost::ExitProcess method [.NET Framework hosting]
- ExitProcess method, ICLRMetaHost interface [.NET Framework hosting]
ms.assetid: b4df98cc-4e4e-407b-b8f4-e0076afef3a4
topic_type:
- apiref
ms.openlocfilehash: 83cbfa097541681305ff285f21c2b6c9c6391ef8
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2020
ms.locfileid: "83703757"
---
# <a name="iclrmetahostexitprocess-method"></a>ICLRMetaHost::ExitProcess 方法
尝试正常关闭所有加载的运行时，然后终止进程。 取代[CorExitProcess](corexitprocess-function.md)函数。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT ExitProcess (  
    [in] INT32 iExitCode);  
```  
  
## <a name="parameters"></a>参数  
 `iExitCode`  
 中进程的退出代码。  
  
## <a name="return-value"></a>返回值  
 此方法从不返回，因此其返回值未定义。  
  
## <a name="remarks"></a>备注  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。  
  
 **标头：** MetaHost  
  
 **库：** 作为资源包括在 Mscoree.dll 中  
  
 **.NET Framework 版本：**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>另请参阅

- [ICLRMetaHost 接口](iclrmetahost-interface.md)
- [承载](index.md)
