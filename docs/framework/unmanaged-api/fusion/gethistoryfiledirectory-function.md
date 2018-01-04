---
title: "GetHistoryFileDirectory 函数"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: GetHistoryFileDirectory
api_location: fusion.dll
api_type: DLLExport
f1_keywords: GetHistoryFileDirectory
helpviewer_keywords: GetHistoryFileDirectory function [.NET Framework fusion]
ms.assetid: 93232222-926e-42ac-b85d-8a6d33977672
topic_type: apiref
caps.latest.revision: "5"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 5d0ec18a4f95d0d280a66b3b9d9200c560f5f187
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="gethistoryfiledirectory-function"></a>GetHistoryFileDirectory 函数
检索应用程序历史记录目录的路径。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT GetHistoryFileDirectory (  
    [in]      LPWSTR      wzDir,  
    [in,out]  LPCWSTR  *pdwsize,  
);  
```  
  
#### <a name="parameters"></a>参数  
 `wzDir`  
 [out]一个缓冲区来保存到应用程序历史记录目录的路径。  
  
 `pdwSize`  
 [在中，out]缓冲区的长度。  
  
## <a name="return-value"></a>返回值  
 此方法返回标准的 COM 错误代码，除了以下值 WinError.h 文件中定义。  
  
|返回代码|描述|  
|-----------------|-----------------|  
|S_OK|该方法已成功完成。|  
|E_INVALIDARG|`wzDir`或`pdwSize`为 null 或版本字符串不正确。|  
  
## <a name="remarks"></a>备注  
 在成功完成，`pdwSize`参数设置为路径的字符串的长度。  
  
## <a name="requirements"></a>惠?  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** Fusion.h  
  
 **库：**为 Fusion.dll 和 Mscorwks.dll。 使用而不是 Mscorwks.dll 为 Fusion.dll 来确保面向.NET Framework 的正确版本。  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]  
  
## <a name="see-also"></a>请参阅  
 [CreateHistoryReader 函数](../../../../docs/framework/unmanaged-api/fusion/createhistoryreader-function.md)  
 [NukeDownloadedCache 函数](../../../../docs/framework/unmanaged-api/fusion/nukedownloadedcache-function.md)  
 [合成全局静态函数](../../../../docs/framework/unmanaged-api/fusion/fusion-global-static-functions.md)
