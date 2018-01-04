---
title: "LoadFromHistory 函数 （WPF 非托管 API 参考）"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: cpp
api_name: LoadFromHistory
api_location: PresentationHost_v0400.dll
ms.assetid: d037c062-a911-4949-b251-ccd3e48b1d17
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 6eca1c30664e381101b6e51c1347341432a042b2
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="loadfromhistory-function-wpf-unmanaged-api-reference"></a>LoadFromHistory 函数 （WPF 非托管 API 参考）
此 API 支持的 Windows Presentation Foundation (WPF) 基础结构，不宜在代码中直接使用。  
  
 Windows Presentation Foundation (WPF) 基础结构用于 windows 管理。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT LoadFromHistory_export(  
        IStream* pHistoryStream,   
        IBindCtx* pBindCtx  
)  
```  
  
#### <a name="parameters"></a>参数  
 pHistoryStream  
 指向历史记录信息的流的指针。  
  
 pBindCtx  
 指向绑定上下文的指针。  
  
## <a name="requirements"></a>惠?  
 **平台：**请参阅[.NET Framework 系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **DLL:**  
  
 在.NET Framework 3.0 和 3.5: PresentationHostDLL.dll  
  
 在.NET Framework 4 及更高版本： PresentationHost_v0400.dll  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]  
  
## <a name="see-also"></a>请参阅  
 [WPF 非托管 API 参考](../../../../docs/framework/wpf/advanced/wpf-unmanaged-api-reference.md)
