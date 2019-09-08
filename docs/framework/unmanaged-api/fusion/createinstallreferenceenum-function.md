---
title: CreateInstallReferenceEnum 函数
ms.date: 03/30/2017
api_name:
- CreateInstallReferenceEnum
api_location:
- fusion.dll
- clr.dll
- mscorwks.dll
api_type:
- DLLExport
f1_keywords:
- CreateInstallReference
helpviewer_keywords:
- CreateInstallReference function [.NET Framework fusion]
ms.assetid: 80dbbbf8-54fc-4894-b74a-0179d3201083
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d696326ff8861ed8496474f76e9eaf89b4ead3e8
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2019
ms.locfileid: "70795402"
---
# <a name="createinstallreferenceenum-function"></a>CreateInstallReferenceEnum 函数
获取一个指针，该指针指向表示应用程序对指定程序集的引用列表的[IInstallReferenceEnum](iinstallreferenceenum-interface.md)实例。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT CreateInstallReferenceEnum (  
    [out] IInstallReferenceEnum **ppRefEnum,  
    [in]  IAssemblyName         *pName,  
    [in]  DWORD                 dwFlags,  
    [in]  LPVOID                pvReserved  
 );  
```  
  
## <a name="parameters"></a>参数  
 `ppRefEnum`  
 弄返回`IInstallReferenceEnum`的指针。  
  
 `pName`  
 中标识要枚举其引用的程序集的[IAssemblyName](iassemblyname-interface.md) 。  
  
 `dwFlags`  
 中影响枚举器行为的标志。  
  
 `pvReserved`  
 中保留以供将来进行扩展。 `pvReserved`必须为空引用。  
  
## <a name="requirements"></a>要求  
 **适用**请参阅[系统需求](../../get-started/system-requirements.md)。  
  
 **标头：** 合成。h  
  
 **类库**合成 .dll 和 Mscorwks.dll。 使用 Mscorwks.dll 而不是来确保目标为正确的 .NET Framework 版本。  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>请参阅

- [IInstallReferenceEnum 接口](iinstallreferenceenum-interface.md)
- [IAssemblyName 接口](iassemblyname-interface.md)
- [合成全局静态函数](fusion-global-static-functions.md)
