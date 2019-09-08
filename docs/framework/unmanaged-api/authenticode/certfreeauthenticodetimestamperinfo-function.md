---
title: CertFreeAuthenticodeTimestamperInfo 函数
ms.date: 03/30/2017
api_name:
- CertFreeAuthenticodeTimestamperInfo
api_location:
- clr.dll
api_type:
- DLLExport
ms.assetid: 3eb14c49-68c2-4516-ac89-e5bd7473831c
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a8ecada29528b065ddad0abc80a850ee0f347f6b
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2019
ms.locfileid: "70787004"
---
# <a name="certfreeauthenticodetimestamperinfo-function"></a>CertFreeAuthenticodeTimestamperInfo 函数
释放为[AXL_AUTHENTICODE_TIMESTAMPER_INFO](axl-authenticode-timestamper-info-structure.md)结构分配的资源。  
  
## <a name="syntax"></a>语法  
  
```cpp  
HRESULT CertFreeAuthenticodeTimestamperInfo (  
    [in, out]  PAXL_AUTHENTICODE_TIMESTAMPER_INFO   pTimestamperInfo  
);  
```  
  
## <a name="parameters"></a>参数  
 `pTimestamperInfo`  
 [in, out] 要释放的时间戳签署人的信息。 请参阅[AXL_AUTHENTICODE_TIMESTAMPER_INFO](axl-authenticode-timestamper-info-structure.md)结构。  
  
## <a name="return-value"></a>返回值  
 如果此函数成功，则返回 `S_OK`。 否则，返回错误代码。  
  
## <a name="see-also"></a>请参阅

- [验证码](index.md)
