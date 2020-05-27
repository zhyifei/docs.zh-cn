---
title: ICeeGen::GetSectionCreate 方法
ms.date: 03/30/2017
api_name:
- ICeeGen.GetSectionCreate
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICeeGen::GetSectionCreate
helpviewer_keywords:
- ICeeGen::GetSectionCreate method [.NET Framework metadata]
- GetSectionCreate method [.NET Framework metadata]
ms.assetid: 154b2460-59ce-4874-a9f2-1b3353486ac5
topic_type:
- apiref
ms.openlocfilehash: 0cf7b15392c90694db659f6faff6feecbef65466
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/27/2020
ms.locfileid: "84008313"
---
# <a name="iceegengetsectioncreate-method"></a>ICeeGen::GetSectionCreate 方法
使用指定的名称和标志值生成并获取代码部分。  
  
 此方法已过时，不应使用。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT GetSectionCreate (  
    [in]  const char     *name,  
    [in]  DWORD          flags,  
    [out] HCEESECTION    *section  
);  
```  
  
## <a name="parameters"></a>参数  
 `name`  
 中指向字符串的指针，该字符串指定要创建的节的名称。  
  
 `flags`  
 中指定选项的标志。  
  
 `section`  
 弄指向新创建的代码部分的指针。  
  
## <a name="remarks"></a>备注  
 `GetSectionCreate`仅当有特殊部分的要求不是由其他方法处理时才调用。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。  
  
 **标头：** Cor  
  
 **库：** 用作 Mscoree.dll 中的资源  
  
 **.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>另请参阅

- [ICeeGen 接口](iceegen-interface.md)
