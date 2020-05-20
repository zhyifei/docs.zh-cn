---
title: CreateICeeFileGen 函数
ms.date: 03/30/2017
api_name:
- CreateICeeFileGen
api_location:
- mscoree.dll
- mscorpehost.dll
- mscorpe.dll
api_type:
- COM
f1_keywords:
- CreateICeeFileGen
helpviewer_keywords:
- CreateICeeFileGen function [.NET Framework hosting]
ms.assetid: e36e1fd8-8456-4359-bdc3-3ec1765f041f
topic_type:
- apiref
ms.openlocfilehash: 294b82efd66704014aab1b73171afe9165f17664
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/19/2020
ms.locfileid: "83616445"
---
# <a name="createiceefilegen-function"></a>CreateICeeFileGen 函数
创建[ICeeFileGen](iceefilegen-class.md)对象。  
  
 此函数已在 .NET Framework 4 中弃用。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT CreateICeeFileGen (  
    [out] ICeeFileGen  **ceeFileGen  
);  
```  
  
## <a name="parameters"></a>参数  
 `ceeFileGen`  
 弄指向新对象的地址的指针 `ICeeFileGen` 。  
  
## <a name="return-value"></a>返回值  
 此方法返回标准 COM 错误代码。  
  
## <a name="remarks"></a>备注  
 `ICeeFileGen`对象用于创建公共语言运行时（CLR）可移植可执行（PE）文件。  
  
 完成后，调用[DestroyICeeFileGen](destroyiceefilegen-function.md)函数以销毁 `ICeeFileGen` 对象。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。  
  
 **标头：** ICeeFileGen  
  
 **库：** MSCorPE  
  
 **.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>另请参阅

- [弃用的 CLR 承载函数](deprecated-clr-hosting-functions.md)
