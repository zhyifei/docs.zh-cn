---
title: _EFN_StackTrace 函数
ms.date: 03/30/2017
api_name:
- _EFN_StackTrace
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- _EFN_StackTrace
helpviewer_keywords:
- _EFN_StackTrace function [.NET Framework debugging]
ms.assetid: caea7754-867c-4360-a65c-5ced4408fd9d
topic_type:
- apiref
ms.openlocfilehash: a725aa2c0f1fdea523bbf7cba880bc805f855782
ms.sourcegitcommit: d9c7ac5d06735a01c1fafe34efe9486734841a72
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/06/2020
ms.locfileid: "82860736"
---
# <a name="_efn_stacktrace-function"></a>\_EFN\_StackTrace 函数
提供托管堆栈跟踪的文本表示形式以及 `CONTEXT` 记录的数组，其中每项对应非托管代码和托管代码之间的每个转换。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT CALLBACK _EFN_StackTrace(  
    [in]  PDEBUG_CLIENT  Client,  
    [out] WCHAR          wszTextOut[],  
    [out] size_t         *puiTextLength,  
    [out] LPVOID         pTransitionContexts,  
    [out] size_t         *puiTransitionContextCount,  
    [in]  size_t         uiSizeOfContext,  
    [in]  DWORD          Flags  
);  
```  
  
## <a name="parameters"></a>参数  
 `Client`  
 中正在调试的客户端。  
  
 `wszTextOut`  
 弄堆栈跟踪的文本表示形式。  
  
 `puiTextLength`  
 弄一个指针，指向中`wszTextOut`的字符数。  
  
 `pTransitionContexts`  
 弄转换上下文的数组。  
  
 `puiTransitionContextCount`  
 弄指向数组中的转换上下文数的指针。  
  
 `uiSizeOfContext`  
 中上下文结构的大小。  
  
 `Flags`  
 中设置为0或 SOS_STACKTRACE_SHOWADDRESSES （0x01）以显示 EBP 寄存器，并在每`module!functionname`行前面设置输入堆栈指针（ESP）。  
  
## <a name="remarks"></a>备注  
 此`_EFN_StackTrace`结构可从 WinDbg 编程界面调用。 参数的使用方式如下：  
  
- 如果`wszTextOut`为 null 且`puiTextLength`不为 null，则该函数将返回中`puiTextLength`的字符串长度。  
  
- 如果`wszTextOut`不为 null，则该函数将文本`wszTextOut`存储到指示的位置`puiTextLength`。 如果缓冲区中有足够的空间，则它将成功返回，如果缓冲区不够长，则返回 E_OUTOFMEMORY。  
  
- 如果`pTransitionContexts`和都为 null， `puiTransitionContextCount`则忽略函数的转换部分。 在这种情况下，函数向调用方提供仅包含函数名称的文本输出。  
  
- 如果`pTransitionContexts`为 null 且`puiTransitionContextCount`不为 null，则该函数将在中`puiTransitionContextCount`返回所需数量的上下文项。  
  
- 如果`pTransitionContexts`不为 null，则函数会将其视为长度`puiTransitionContextCount`的结构数组。 结构大小由`uiSizeOfContext`指定，并且必须是[SimpleContext](stacktrace-simplecontext-structure.md)的大小或`CONTEXT`体系结构的大小。  
  
- `wszTextOut`采用以下格式编写：  
  
    ```output  
    "<ModuleName>!<Function Name>[+<offset in hex>]  
    ...  
    (TRANSITION)  
    ..."  
    ```  
  
- 如果偏移量（十六进制）为0x0，则不写入偏移量。  
  
- 如果线程上当前没有托管代码，该函数将返回 SOS_E_NOMANAGEDCODE。  
  
- `Flags`参数为0或 SOS_STACKTRACE_SHOWADDRESSES，以在每`module!functionname`行的前面显示 EBP 和 ESP。 默认情况下，它是0。  
  
    ```cpp  
    #define SOS_STACKTRACE_SHOWADDRESSES   0x00000001  
    ```  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。  
  
 **标头：** SOS_Stacktrace。h  
  
 **.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>另请参阅

- [调试全局静态函数](debugging-global-static-functions.md)
