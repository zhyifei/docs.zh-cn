---
title: Authenticode（非托管 API 参考）
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: reference
ms.assetid: 7e8cc303-6e77-4116-aa8b-7ea297a3a467
caps.latest.revision: 4
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 0b790064ef64ab44f3798a62d5dbf004f0f0bba6
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="authenticode-unmanaged-api-reference"></a>Authenticode（非托管 API 参考）
支持验证码 XrML 许可证创建和验证模块。  
  
## <a name="in-this-section"></a>本节内容  
 [_AxlGetIssuerPublicKeyHash 函数](../../../../docs/framework/unmanaged-api/authenticode/axlgetissuerpublickeyhash-function.md)  
 检索与用于对指定证书进行签名的私钥关联的公钥的 SHA-1 哈希。  
  
 [_AxlPublicKeyBlobToPublicKeyToken 函数](../../../../docs/framework/unmanaged-api/authenticode/axlpublickeyblobtopublickeytoken-function.md)  
 从 CSP PUBLICKEYBLOB 格式计算强名称公钥标记。  
  
 [_AxlRSAKeyValueToPublicKeyToken 函数](../../../../docs/framework/unmanaged-api/authenticode/axlrsakeyvaluetopublickeytoken-function.md)  
 将模数和指数转换为强名称公钥标记。  
  
 [CertFreeAuthenticodeSignerInfo 函数](../../../../docs/framework/unmanaged-api/authenticode/certfreeauthenticodesignerinfo-function.md)  
 释放为 AXL_AUTHENTICODE_SIGNER_INFO 结构分配的资源。  
  
 [CertFreeAuthenticodeTimestamperInfo 函数](../../../../docs/framework/unmanaged-api/authenticode/certfreeauthenticodetimestamperinfo-function.md)  
 释放为 AXL_AUTHENTICODE_TIMESTAMPER_INFO 结构分配的资源。  
  
 [CertTimestampAuthenticodeLicense 函数](../../../../docs/framework/unmanaged-api/authenticode/certtimestampauthenticodelicense-function.md)  
 为由 CertCreateAuthenticodeLicense 创建的验证码 XrML 许可证添加时间戳。  
  
 [CertVerifyAuthenticodeLicense 函数](../../../../docs/framework/unmanaged-api/authenticode/certverifyauthenticodelicense-function.md)  
 验证验证码 XrML 许可证的有效性。  
  
 [AXL_AUTHENTICODE_SIGNER_INFO 结构](../../../../docs/framework/unmanaged-api/authenticode/axl-authenticode-signer-info-structure.md)  
 定义验证码签署人的信息。  
  
 [AXL_AUTHENTICODE_TIMESTAMPER_INFO 结构](../../../../docs/framework/unmanaged-api/authenticode/axl-authenticode-timestamper-info-structure.md)  
 定义验证码时间戳签署人的信息。  
  
## <a name="see-also"></a>请参阅  
 [非托管 API 参考](../../../../docs/framework/unmanaged-api/index.md)
