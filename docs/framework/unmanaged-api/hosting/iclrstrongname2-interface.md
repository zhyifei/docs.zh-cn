---
title: ICLRStrongName2 接口
ms.date: 03/30/2017
api_name:
- ICLRStrongName2
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName2
helpviewer_keywords:
- ICLRStrongName2 interface [.NET Framework hosting]
ms.assetid: 9f098a74-201e-4628-a468-8dee9ab99b4a
topic_type:
- apiref
ms.openlocfilehash: bc871c29f53a9ea4451a0fc1c747939724b0da87
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73092247"
---
# <a name="iclrstrongname2-interface"></a>ICLRStrongName2 接口
提供使用 SHA-1 安全哈希算法（SHA-256、SHA-384 和 SHA-512）组创建强名称的功能。  
  
## <a name="methods"></a>方法  
  
|方法|描述|  
|------------|-----------------|  
|[StrongNameGetPublicKeyEx 方法](../../../../docs/framework/unmanaged-api/hosting/strongnamegetpublickeyex-method.md)|获取公钥/私钥对中的公钥，并指定哈希算法和签名算法。|  
|[StrongNameSignatureVerificationEx2 方法](../../../../docs/framework/unmanaged-api/hosting/strongnamesignatureverificationex2-method.md)|验证强名称程序集的签名，并提供从 ECMA 密钥到实际密钥的映射。|  
  
## <a name="remarks"></a>备注  
  
## <a name="requirements"></a>要求  
 **平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **标头：** MetaHost  
  
 **库：** 作为资源包括在 Mscoree.dll 中  
  
 **.NET Framework 版本：** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]
