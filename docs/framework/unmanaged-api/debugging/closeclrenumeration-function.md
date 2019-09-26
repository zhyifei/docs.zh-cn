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
ms.openlocfilehash: 3a05a779d4a56eb8f881da1824d5ffaa363b5a01
ms.sourcegitcommit: 3caa92cb97e9f6c31f21769c7a3f7c4304024b39
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/25/2019
ms.locfileid: "71274282"
---
# <a name="closeclrenumeration-function"></a>CloseCLREnumeration 函数
关闭位于[EnumerateCLRs 函数](enumerateclrs-function.md)所返回的句柄数组中的所有有效的公共语言运行时（CLR）继续启动事件，并释放该句柄和字符串路径数组的内存。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT CloseCLREnumeration (  
    [in]  DWORD      pHandleArray,  
    [in]  LPWSTR**   pStringArray,  
    [in]  DWORD*     dwArrayLength  
);  
```  
  
## <a name="parameters"></a>参数  
 `pHandleArray`  
 中指向从[EnumerateCLRs 函数](enumerateclrs-function.md)返回的事件句柄的数组的指针。  
  
 `pStringArray`  
 中一个指针，指向从[EnumerateCLRs 函数](enumerateclrs-function.md)返回的 CLR 字符串路径的数组。  
  
 `dwArrayLength`  
 [in] 包含 `pHandleArray` 或 `pStringArray`大小（长度）（它们是相同）的 DWORD。  
  
## <a name="return-value"></a>返回值  
 S_OK  
 [EnumerateCLRs 函数](enumerateclrs-function.md)打开的句柄将关闭，并且将释放分配给句柄和字符串数组的内存。  
  
 E_INVALIDARG  
 `pHandleArray` 的长度与传入 `dwArrayLength` 的长度不匹配。  
  
 E_FAIL（或其他 E_ 返回代码）  
 此函数无法释放 `pHandleArray` 和 `pStringArray` 的内存。  
  
## <a name="requirements"></a>要求  
 **适用**请参阅[系统需求](../../get-started/system-requirements.md)。  
  
 **标头：** dbgshim.dll  
  
 **库：** dbgshim.dll  
  
 **.NET Framework 版本：** 3.5 SP1
