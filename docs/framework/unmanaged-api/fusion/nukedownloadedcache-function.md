---
title: "NukeDownloadedCache 函数"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- NukeDownloadedCache
api_location:
- fusion.dll
- clr.dll
- mscorwks.dll
api_type:
- DLLExport
f1_keywords:
- NukeDownloadedCache
helpviewer_keywords:
- NukeDownloadedCache function [.NET Framework fusion]
ms.assetid: fac2b1c6-6fa3-4818-805b-b63972024c86
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 31d7ba7d5f4a9268ea1e04a4c9f09cd17ebfd5bb
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="nukedownloadedcache-function"></a>NukeDownloadedCache 函数
删除公共语言运行时 (CLR) 下载缓存。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT NukeDownloadedCache();  
```  
  
## <a name="return-value"></a>返回值  
 WinError.h 中定义，此方法将返回标准的 COM 错误代码。  
  
## <a name="remarks"></a>备注  
 CLR 下载缓存是具有强名称程序集，从某个 URL 下载以备可能重复使用的存储位置的区域。  
  
## <a name="requirements"></a>惠?  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** Fusion.h  
  
 **库：**为 Fusion.dll 和 Mscorwks.dll。 使用而不是 Mscorwks.dll 为 Fusion.dll 来确保面向.NET Framework 的正确版本。  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]  
  
## <a name="see-also"></a>请参阅  
 [CreateHistoryReader 函数](../../../../docs/framework/unmanaged-api/fusion/createhistoryreader-function.md)  
 [GetHistoryFileDirectory 函数](../../../../docs/framework/unmanaged-api/fusion/gethistoryfiledirectory-function.md)  
 [合成全局静态函数](../../../../docs/framework/unmanaged-api/fusion/fusion-global-static-functions.md)
