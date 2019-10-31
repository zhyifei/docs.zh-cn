---
title: CreateHistoryReader 函数
ms.date: 03/30/2017
api_name:
- CreateHistoryReader
api_location:
- fusion.dll
api_type:
- DLLExport
f1_keywords:
- CreateHistoryReader
helpviewer_keywords:
- CreateHistoryReader function [.NET Framework fusion]
ms.assetid: 66a89acf-8c32-44c0-8787-960c99c7b3ec
topic_type:
- apiref
ms.openlocfilehash: 80979f0424469bb1d4771ad6507bb8c9d5364ab4
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73108607"
---
# <a name="createhistoryreader-function"></a>CreateHistoryReader 函数
为指定的文件创建历史记录读取器。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT CreateHistoryReader (  
    [in]  LPCWSTR        wzFilePath,  
    [out] IHistoryReader **ppHistoryReader  
 );  
```  
  
## <a name="parameters"></a>参数  
 `wzFilePath`  
 中文件路径。  
  
 `ppHistoryReader`  
 弄成功完成后，包含指向历史记录读取器的指针。  
  
## <a name="return-value"></a>返回值  
 此方法返回 Winerror.h 中定义的标准 COM 错误代码，以及下表中描述的值。  
  
|返回代码|描述|  
|-----------------|-----------------|  
|S_OK|指示该方法已成功完成。|  
|E_INVALIDARG|指示 `wzFilePath` 或 `ppHistoryReader` 设置为空引用。|  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。  
  
 **库：** 合成 .dll  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>请参阅

- [合成全局静态函数](fusion-global-static-functions.md)
