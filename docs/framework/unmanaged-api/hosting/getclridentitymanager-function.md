---
title: GetCLRIdentityManager 函数
ms.date: 03/30/2017
api_name:
- GetCLRIdentityManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- GetCLRIdentityManager
helpviewer_keywords:
- GetCLRIdentityManager function [.NET Framework hosting]
ms.assetid: 66eeca30-adb4-45f4-aff5-347564c95724
topic_type:
- apiref
ms.openlocfilehash: 57f771d933e896677dfc0bd5d9dac58da2af22c8
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/19/2020
ms.locfileid: "83617251"
---
# <a name="getclridentitymanager-function"></a>GetCLRIdentityManager 函数
获取一个指向接口的指针，该接口允许公共语言运行时（CLR）管理标识。  
  
 此函数已在 .NET Framework 4 中弃用。  
  
## <a name="syntax"></a>语法  
  
```cpp  
STDAPI GetCLRIdentityManager(  
    [in]  REFIID      riid,  
    [out] IUnknown  **ppManager  
);  
```  
  
## <a name="parameters"></a>参数  
 `riid`  
 中一个 `REFIID` （接口标识符），它指定要获取的接口。 此值必须是 IID_ICLRAssemblyIdentityManager 或 IID_ICLRHostBindingPolicyManager。  
  
 `ppManager`  
 弄指向[ICLRAssemblyIdentityManager](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)或[ICLRHostBindingPolicyManager](iclrhostbindingpolicymanager-interface.md)对象地址的指针。  
  
## <a name="remarks"></a>备注  
 调用[GetRealProcAddress](getrealprocaddress-function.md)函数以获取指向函数的指针 `GetCLRIdentityManager` 。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。  
  
 **标头：** Mscoree.dll  
  
 **库：** Mscorwks.dll  
  
 **.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>另请参阅

- [弃用的 CLR 承载函数](deprecated-clr-hosting-functions.md)
