---
title: NukeDownloadedCache 函数
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 29f492173a7fd22ab497d6e0096798e164fccf26
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2019
ms.locfileid: "70796305"
---
# <a name="nukedownloadedcache-function"></a>NukeDownloadedCache 函数
删除公共语言运行时（CLR）下载缓存。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT NukeDownloadedCache();  
```  
  
## <a name="return-value"></a>返回值  
 此方法返回 Winerror.h 中定义的标准 COM 错误代码。  
  
## <a name="remarks"></a>备注  
 CLR 下载缓存是存储从 URL 下载的具有强名称的程序集以便可以重复使用的区域。  
  
## <a name="requirements"></a>要求  
 **适用**请参阅[系统需求](../../get-started/system-requirements.md)。  
  
 **标头：** 合成。h  
  
 **类库**合成 .dll 和 Mscorwks.dll。 使用 Mscorwks.dll 而不是来确保目标为正确的 .NET Framework 版本。  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]  
  
## <a name="see-also"></a>请参阅

- [CreateHistoryReader 函数](createhistoryreader-function.md)
- [GetHistoryFileDirectory 函数](gethistoryfiledirectory-function.md)
- [合成全局静态函数](fusion-global-static-functions.md)
