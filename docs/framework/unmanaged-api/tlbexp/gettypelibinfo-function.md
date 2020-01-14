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
ms.openlocfilehash: 4f05eb2e6ef31cf1993a623c38bb177f7e3c297e
ms.sourcegitcommit: 7e2128d4a4c45b4274bea3b8e5760d4694569ca1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/14/2020
ms.locfileid: "75935651"
---
# <a name="gettypelibinfo-function"></a>GetTypeLibInfo 函数
通过检查指定类型库的[TLIBATTR](/windows/win32/api/oaidl/ns-oaidl-tlibattr)结构来返回相关信息。  
  
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
 弄标识库的目标操作系统的[SYSKIND](/windows/win32/api/oaidl/ne-oaidl-syskind)标志。 常用值为 SYS_WIN32 和 SYS_WIN64。  
  
 `pTypeLibMajorVer`  
 弄类型库的主版本号。 例如，对于版本*x. y*，主版本号是*x*。  
  
 `pTypeLibMinorVer`  
 弄类型库的次版本号。 例如，对于版本*x. y*，次版本号为*y*。  
  
## <a name="remarks"></a>备注  
 `GetTypeLibInfo` 函数由[tlbexp.exe （类型库导出程序）](../../tools/tlbexp-exe-type-library-exporter.md)调用。 此工具将生成一个类型库，该类型库描述公共语言运行时（CLR）程序集中的类型。  
  
 如果任何参数为 null，则该函数将返回 `HRESULT` 的 `E_POINTER`。 否则，它将返回 `S_OK`。  
  
## <a name="requirements"></a>需求  
 **平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。  
  
 **标头：** TlbRef  
  
 **库：** TlbRef  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>另请参阅

- [Tlbexp Helper 函数](index.md)
- [LoadTypeLibEx 函数](https://docs.microsoft.com/previous-versions/windows/desktop/api/oleauto/nf-oleauto-loadtypelibex)
