---
title: ICeeGen::GetSectionBlock 方法
ms.date: 03/30/2017
api_name:
- ICeeGen.GetSectionBlock
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICeeGen::GetSectionBlock
helpviewer_keywords:
- GetSectionBlock method [.NET Framework metadata]
- ICeeGen::GetSectionBlock method [.NET Framework metadata]
ms.assetid: 05c78aaf-5bbd-497e-9ae2-55f4fae0c5fb
topic_type:
- apiref
ms.openlocfilehash: ed534890fc90d3b8543a1166c85903f10163f0a8
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/27/2020
ms.locfileid: "84008310"
---
# <a name="iceegengetsectionblock-method"></a>ICeeGen::GetSectionBlock 方法
获取代码库的节块。  
  
 此方法已过时，不应使用。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT GetSectionBlock (  
    [in]  HCEESECTION    section,
    [in]  ULONG          len,  
    [in]  ULONG          align     = 1,  
    [out] void           **ppBytes = 0  
);
```  
  
## <a name="parameters"></a>参数  
 `section`  
 中要从中检索基本代码块的部分。  
  
 `len`  
 中要检索的块的长度。  
  
 `align`  
 中相对于部分开头的字节，用于对齐块的第一个字节。 这是块在节中的位置。  
  
 `ppBytes`  
 弄一个指针，指向接收检索到的块的地址的位置。  
  
## <a name="remarks"></a>备注  
 `GetSectionBlock`仅当有特殊部分的要求不是由其他方法处理时才调用。  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。  
  
 **标头：** Cor  
  
 **库：** 用作 Mscoree.dll 中的资源  
  
 **.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>另请参阅

- [ICeeGen 接口](iceegen-interface.md)
