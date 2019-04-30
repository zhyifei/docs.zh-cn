---
title: SaveToHistory 函数 （WPF 非托管 API 参考）
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- SaveToHistory
api_location:
- PresentationHost_v0400.dll
ms.assetid: 6dd101a3-44ad-4143-b228-772156f9b8ff
ms.openlocfilehash: 3f6413558ff1f259e497c6a1c31eb2664f70cc48
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "62053452"
---
# <a name="savetohistory-function-wpf-unmanaged-api-reference"></a>SaveToHistory 函数 （WPF 非托管 API 参考）
此 API 支持 Windows Presentation Foundation (WPF) 基础结构，不应在代码中直接使用。  
  
 Windows Presentation Foundation (WPF) 基础结构使用的 windows 管理。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT SaveToHistory(  
   __in_ecount(1) IStream* pHistoryStream  
)  
```  
  
## <a name="parameters"></a>参数  
 pHistoryStream  
 一个指向历史记录流。  
  
## <a name="requirements"></a>要求  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[.NET Framework 系统需求](../../get-started/system-requirements.md)。  
  
 **DLL:**  
  
 在.NET Framework 3.0 和 3.5:PresentationHostDLL.dll  
  
 在.NET Framework 4 及更高版本：PresentationHost_v0400.dll  
  
 **.NET framework 版本：** [!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]  
  
## <a name="see-also"></a>请参阅

- [WPF 非托管 API 参考](wpf-unmanaged-api-reference.md)
