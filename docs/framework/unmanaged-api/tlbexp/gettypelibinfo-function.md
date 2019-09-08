---
title: GetTypeLibInfo 函数
ms.date: 03/30/2017
api_name:
- GetTypeLibInfo
api_location:
- TlbRef.dll
api_type:
- DLLExport
f1_keywords:
- GetTypeLibInfo
helpviewer_keywords:
- GetTypeLibInfo function [.NET Framework]
ms.assetid: a1c4d165-9bdc-4ca8-940e-292d4ffcc338
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d8ea7df9396e9199d04ad5609daa9d2b01761f36
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2019
ms.locfileid: "70798889"
---
# <a name="gettypelibinfo-function"></a>GetTypeLibInfo 函数
通过检查指定类型库的[TLIBATTR](https://docs.microsoft.com/windows/win32/api/oaidl/ns-oaidl-tlibattr)结构来返回相关信息。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT GetTypeLibInfo(  
    [in]   LPWSTR     szFile,  
    [out]  GUID      *pTypeLibID,  
    [out]  LCID      *pTypeLibLCID,  
    [out]  SYSKIND   *pTypeLibPlatform,  
    [out]  USHORT    *pTypeLibMajorVer,  
    [out]  USHORT    *pTypeLibMinorVer  
);  
```  
  
## <a name="parameters"></a>参数  
 `szFile`  
 中类型库的文件名。  
  
 `pTypeLibID`  
 弄类型库的 GUID。  
  
 `pTypeLibLCID`  
 弄类型库的本地化 ID。  
  
 `pTypeLibPlatform`  
 弄标识库的目标操作系统的[SYSKIND](https://docs.microsoft.com/windows/win32/api/oaidl/ne-oaidl-syskind)标志。 常见值为 SYS_WIN32 和 SYS_WIN64。  
  
 `pTypeLibMajorVer`  
 弄类型库的主版本号。 例如，对于版本*x. y*，主版本号是*x*。  
  
 `pTypeLibMinorVer`  
 弄类型库的次版本号。 例如，对于版本*x. y*，次版本号为*y*。  
  
## <a name="remarks"></a>备注  
 此`GetTypeLibInfo`函数由[tlbexp.exe （类型库导出程序）](../../tools/tlbexp-exe-type-library-exporter.md)调用。 此工具将生成一个类型库，该类型库描述公共语言运行时（CLR）程序集中的类型。  
  
 如果任何参数为 null，则函数返回`HRESULT`的。 `E_POINTER` 否则，它将返回 `S_OK`。  
  
## <a name="requirements"></a>要求  
 **适用**请参阅[系统需求](../../get-started/system-requirements.md)。  
  
 **标头：** TlbRef  
  
 **类库**TlbRef.lib  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>请参阅

- [Tlbexp Helper 函数](index.md)
- [LoadTypeLibEx 函数](https://docs.microsoft.com/previous-versions/windows/desktop/api/oleauto/nf-oleauto-loadtypelibex)
