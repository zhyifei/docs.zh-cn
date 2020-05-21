---
title: ICLRStrongName::StrongNameCompareAssemblies 方法
ms.date: 03/30/2017
api_name:
- ICLRStrongName.StrongNameCompareAssemblies
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::StrongNameCompareAssemblies
helpviewer_keywords:
- ICLRStrongName::StrongNameCompareAssemblies method [.NET Framework hosting]
- StrongNameCompareAssemblies method, ICLRStrongName interface [.NET Framework hosting]
ms.assetid: b1fb356c-72cf-4aa4-8376-f291a6d97c01
topic_type:
- apiref
ms.openlocfilehash: 0087636c68d0748ad2b143de9b132278ab9d43f5
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/21/2020
ms.locfileid: "83762053"
---
# <a name="iclrstrongnamestrongnamecompareassemblies-method"></a>ICLRStrongName::StrongNameCompareAssemblies 方法
确定两个程序集是否仅是强名称签名不同。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT StrongNameCompareAssemblies (  
    [in]  LPCWSTR   wszAssembly1,  
    [in]  LPCWSTR   wszAssembly2,  
    [out] DWORD     *pdwResult  
);  
```  
  
## <a name="parameters"></a>参数  
 `wszAssembly1`  
 中第一个程序集的路径。  
  
 `wszAssembly2`  
 中第二个程序集的路径。  
  
 `pdwResult`  
 弄以下值之一：  
  
- `SN_CMP_DIFFERENT`（0）-指定程序集包含不同的数据。  
  
- `SN_CMP_IDENTICAL`（1）-指定程序集完全相同，包括它们的签名和校验和。  
  
- `SN_CMP_SIGONLY`（2）-指定程序集不同于签名和校验和。  
  
## <a name="return-value"></a>返回值  
 `S_OK`如果该方法已成功完成，则为;否则，表示失败的 HRESULT 值（请参阅列表的[常见 HRESULT 值](/windows/win32/seccrypto/common-hresult-values)）。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。  
  
 **标头：** MetaHost  
  
 **库：** 作为资源包括在 Mscoree.dll 中  
  
 **.NET Framework 版本：**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="remarks"></a>注解  
 程序集的强名称签名由程序集的文本名称、版本、区域性和公钥标记组成。  
  
## <a name="see-also"></a>另请参阅

- [ICLRStrongName 接口](iclrstrongname-interface.md)
