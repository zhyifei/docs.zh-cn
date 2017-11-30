---
title: "CreateHistoryReader 函数"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CreateHistoryReader
api_location: fusion.dll
api_type: DLLExport
f1_keywords: CreateHistoryReader
helpviewer_keywords: CreateHistoryReader function [.NET Framework fusion]
ms.assetid: 66a89acf-8c32-44c0-8787-960c99c7b3ec
topic_type: apiref
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 4f4b09f592a27b7d3d25b2dbe13be7e261023bf5
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="createhistoryreader-function"></a>CreateHistoryReader 函数
创建指定的文件历史记录读取器。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT CreateHistoryReader (  
    [in]  LPCWSTR        wzFilePath,  
    [out] IHistoryReader **ppHistoryReader  
 );  
```  
  
#### <a name="parameters"></a>参数  
 `wzFilePath`  
 [in]文件路径中。  
  
 `ppHistoryReader`  
 [out]在成功完成，包含指向历史记录读取器的指针。  
  
## <a name="return-value"></a>返回值  
 定义在 WinError.h，除了下表中描述的值，此方法将返回标准的 COM 错误代码。  
  
|返回代码|描述|  
|-----------------|-----------------|  
|S_OK|指示已成功完成的方法。|  
|E_INVALIDARG|指示`wzFilePath`或`ppHistoryReader`设置为 null 引用。|  
  
## <a name="requirements"></a>要求  
 **平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **库：**为 Fusion.dll  
  
 **.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>另请参阅  
 [合成全局静态函数](../../../../docs/framework/unmanaged-api/fusion/fusion-global-static-functions.md)
