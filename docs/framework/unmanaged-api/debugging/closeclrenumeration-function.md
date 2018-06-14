---
title: CloseCLREnumeration 函数
ms.date: 03/30/2017
api_name:
- CloseCLREnumeration
api_location:
- dbgshim.dll
api_type:
- COM
f1_keywords:
- CloseCLREnumeration
helpviewer_keywords:
- debugging API [Silverlight]
- Silverlight, debugging
- CloseCLR Enumeration function
ms.assetid: 5e3c3958-80bb-43b1-a96b-dd3e6dbd9cd7
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 18903bd00b0a9d09365d03c155531a25dc013189
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33406083"
---
# <a name="closeclrenumeration-function"></a>CloseCLREnumeration 函数
关闭任何有效的公共语言运行时 (CLR) 继续启动事件位于返回的句柄数组[EnumerateCLRs 函数](../../../../docs/framework/unmanaged-api/debugging/enumerateclrs-function.md)，并释放句柄和字符串路径数组的内存。  
  
## <a name="syntax"></a>语法  
  
```  
HRESULT CloseCLREnumeration (  
    [in]  DWORD      pHandleArray,  
    [in]  LPWSTR**   pStringArray,  
    [in]  DWORD*     dwArrayLength  
);  
```  
  
#### <a name="parameters"></a>参数  
 `pHandleArray`  
 [in]从返回事件句柄数组的指针[EnumerateCLRs 函数](../../../../docs/framework/unmanaged-api/debugging/enumerateclrs-function.md)。  
  
 `pStringArray`  
 [in]指向从返回的 CLR 字符串路径数组的[EnumerateCLRs 函数](../../../../docs/framework/unmanaged-api/debugging/enumerateclrs-function.md)。  
  
 `dwArrayLength`  
 [in] 包含 `pHandleArray` 或 `pStringArray`大小（长度）（它们是相同）的 DWORD。  
  
## <a name="return-value"></a>返回值  
 S_OK  
 通过打开的句柄[EnumerateCLRs 函数](../../../../docs/framework/unmanaged-api/debugging/enumerateclrs-function.md)均已关闭，并且将释放句柄和字符串数组分配内存。  
  
 E_INVALIDARG  
 `pHandleArray` 的长度与传入 `dwArrayLength` 的长度不匹配。  
  
 E_FAIL（或其他 E_ 返回代码）  
 此函数无法释放 `pHandleArray` 和 `pStringArray` 的内存。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** dbgshim.h  
  
 **库：** dbgshim.dll  
  
 **.NET framework 版本：** 3.5 SP1
