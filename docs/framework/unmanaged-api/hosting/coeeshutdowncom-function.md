---
title: "CoEEShutDownCOM 函数"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CoEEShutDownCOM
api_location:
- mscoree.dll
- clr.dll
- mscorwks.dll
- mscoreei.dll
api_type: DLLExport
f1_keywords: CoEEShutDownCOM
helpviewer_keywords: CoEEShutDownCOM function [.NET Framework hosting]
ms.assetid: b634cae2-632f-4737-9be4-92d0652844d7
topic_type: apiref
caps.latest.revision: "18"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 0ae339310c2bfd186cae798ff603d69735abeefd
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="coeeshutdowncom-function"></a>CoEEShutDownCOM 函数
强制公共语言运行时 (CLR) 来释放它在运行时可调用包装 (RCW) 内包含的所有接口指针。 此操作将释放 RCW 的所有缓存。 中已弃用此全局函数[!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)]。 相反，针对特定运行时使用的入口点。  
  
## <a name="syntax"></a>语法  
  
```  
void CoEEShutDownCOM ();  
```  
  
## <a name="remarks"></a>备注  
 `CoEEShutDownCOM`函数首先释放所有 Rcw 所有上下文在和中的所有缓存，并将删除现有的安装程序中任何拆除通知。 没有 DLL 卸载时发生。  
  
> [!CAUTION]
>  此函数会影响所有加载到进程的运行时。  
  
 开头[!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)]，调用此函数对你想要影响特定运行时的入口点。 若要获取的入口点，请调用[iclrruntimeinfo:: Getprocaddress](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-getprocaddress-method.md)方法并指定"CoEEShutDownCOM"。  
  
## <a name="requirements"></a>惠?  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** Cor.h  
  
 **库：**作为 MsCorEE.dll 中的资源  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>请参阅  
 [元数据全局静态函数](../../../../docs/framework/unmanaged-api/metadata/metadata-global-static-functions.md)
