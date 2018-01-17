---
title: "强命名（非托管 API 参考）"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
helpviewer_keywords:
- strong naming [.NET Framework], using the unmanaged API
- native API reference [.NET Framework], strong naming
- unmanaged API reference [.NET Framework], strong naming
ms.assetid: 428c68b6-a7b4-44be-b280-75905f46612c
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 2127cdb1178da37bcfe77a0e1a02ccd34be2d800
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="strong-naming-unmanaged-api-reference"></a>强命名（非托管 API 参考）
强命名 API 允许客户端管理的程序集强名称签名。  
  
 使用强名称对程序集进行签名将向包含程序集清单的文件添加公钥加密。 强名称签名帮助验证名称的唯一性，避免名称欺骗，并解析引用时将调用方提供的唯一标识。 但是，没有的信任级别都具有强名称相关联。  
  
## <a name="in-this-section"></a>本节内容  
 [强命名的全局静态函数](http://msdn.microsoft.com/en-us/efa715df-e8cc-48f2-9ec4-26586f0dc8d0)  
 描述强命名 API 使用的非托管全局静态函数。  
  
> [!NOTE]
>  所有这些函数已弃用开头[!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)]。 建议的替代，请参阅[ICLRStrongName](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)接口。  
  
 [GetHashFromAssemblyFile 函数](../../../../docs/framework/unmanaged-api/strong-naming/gethashfromassemblyfile-function.md)  
 获取使用指定的哈希算法对指定的程序集文件的哈希值。 从开始弃用的[!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)]。  
  
 [GetHashFromAssemblyFileW 函数](../../../../docs/framework/unmanaged-api/strong-naming/gethashfromassemblyfilew-function.md)  
 获取为 Unicode 字符串，使用指定的哈希算法指定的程序集文件的哈希值。 从开始弃用的[!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)]。  
  
 [GetHashFromBlob 函数](../../../../docs/framework/unmanaged-api/strong-naming/gethashfromblob-function.md)  
 获取指定的内存地址，使用指定的哈希算法的程序集哈希值。 从开始弃用的[!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)]。  
  
 [GetHashFromFile 函数](../../../../docs/framework/unmanaged-api/strong-naming/gethashfromfile-function.md)  
 生成指定的文件的内容哈希代码。  从开始弃用的[!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)]。  
  
 [GetHashFromFileW 函数](../../../../docs/framework/unmanaged-api/strong-naming/gethashfromfilew-function.md)  
 生成指定的 Unicode 字符串的文件的内容哈希代码。 从开始弃用的[!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)]。  
  
 [GetHashFromHandle 函数](../../../../docs/framework/unmanaged-api/strong-naming/gethashfromhandle-function.md)  
 生成与指定的文件句柄，使用指定的哈希算法文件的内容哈希代码。  从开始弃用的[!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)]。  
  
 [StrongNameCompareAssemblies 函数](../../../../docs/framework/unmanaged-api/strong-naming/strongnamecompareassemblies-function.md)  
 确定是否两个程序集的差异仅在于其强名称签名。 从开始弃用的[!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)]。  
  
 [StrongNameErrorInfo 函数](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md)  
 获取引发的强名称函数之一的最后一个错误代码。  
  
 [StrongNameFreeBuffer 函数](../../../../docs/framework/unmanaged-api/strong-naming/strongnamefreebuffer-function.md)  
 释放通过以前对强名称函数调用如分配的内存[StrongNameGetPublicKey](../../../../docs/framework/unmanaged-api/strong-naming/strongnamegetpublickey-function.md)， [StrongNameTokenFromPublicKey](../../../../docs/framework/unmanaged-api/strong-naming/strongnametokenfrompublickey-function.md)，或[StrongNameSignatureGeneration](../../../../docs/framework/unmanaged-api/strong-naming/strongnamesignaturegeneration-function.md).   从开始弃用的[!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)]。  
  
 [StrongNameGetBlob 函数](../../../../docs/framework/unmanaged-api/strong-naming/strongnamegetblob-function.md)  
 用的二进制表示形式指定地址处的可执行文件填充指定的缓冲区。 从开始弃用的[!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)]。  
  
 [StrongNameGetBlobFromImage 函数](../../../../docs/framework/unmanaged-api/strong-naming/strongnamegetblobfromimage-function.md)  
 获取位于指定的内存地址处的二进制表示形式的程序集映像。 从开始弃用的[!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)]。  
  
 [StrongNameGetPublicKey 函数](../../../../docs/framework/unmanaged-api/strong-naming/strongnamegetpublickey-function.md)  
 获取从私钥/公钥对的公钥。 从开始弃用的[!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)]。  
  
 [StrongNameHashSize 函数](../../../../docs/framework/unmanaged-api/strong-naming/strongnamehashsize-function.md)  
 获取使用指定的哈希算法的哈希所需的缓冲区大小。  从开始弃用的[!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)]。  
  
 [StrongNameKeyDelete 函数](../../../../docs/framework/unmanaged-api/strong-naming/strongnamekeydelete-function.md)  
 删除指定的密钥容器。 从开始弃用的[!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)]。  
  
 [StrongNameKeyGen 函数](../../../../docs/framework/unmanaged-api/strong-naming/strongnamekeygen-function.md)  
 创建强名称使用新的公钥/私钥密钥对。  从开始弃用的[!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)]。  
  
 [StrongNameKeyGenEx 函数](../../../../docs/framework/unmanaged-api/strong-naming/strongnamekeygenex-function.md)  
 生成具有强名称用于指定的密钥大小的新公钥/私钥密钥对。 从开始弃用的[!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)]。  
  
 [StrongNameKeyInstall 函数](../../../../docs/framework/unmanaged-api/strong-naming/strongnamekeyinstall-function.md)  
 将公钥/私钥对导入容器。  从开始弃用的[!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)]。  
  
 [StrongNameSignatureGeneration 函数](../../../../docs/framework/unmanaged-api/strong-naming/strongnamesignaturegeneration-function.md)  
 为指定的程序集生成强名称签名。   从开始弃用的[!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)]。  
  
 [StrongNameSignatureGenerationEx 函数](../../../../docs/framework/unmanaged-api/strong-naming/strongnamesignaturegenerationex-function.md)  
 基于指定的标志指定的程序集生成强名称签名。    从开始弃用的[!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)]。  
  
 [StrongNameSignatureSize 函数](../../../../docs/framework/unmanaged-api/strong-naming/strongnamesignaturesize-function.md)  
 返回强名称签名的大小。 从开始弃用的[!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)]。  
  
 [StrongNameSignatureVerification 函数](../../../../docs/framework/unmanaged-api/strong-naming/strongnamesignatureverification-function.md)  
 获取一个值，该值在提供的路径的程序集清单是否包含强名称签名，验证根据指定的标志。 从开始弃用的[!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)]。  
  
 [StrongNameSignatureVerificationEx 函数](../../../../docs/framework/unmanaged-api/strong-naming/strongnamesignatureverificationex-function.md)  
 获取一个值，该值在提供的路径的程序集清单是否包含强名称签名。  从开始弃用的[!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)]。  
  
 [StrongNameSignatureVerificationFromImage 函数](../../../../docs/framework/unmanaged-api/strong-naming/strongnamesignatureverificationfromimage-function.md)  
 验证已映射到内存的程序集关联的公钥无效。 从开始弃用的[!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)]。  
  
 [StrongNameTokenFromAssembly 函数](../../../../docs/framework/unmanaged-api/strong-naming/strongnametokenfromassembly-function.md)  
 从指定的程序集文件中创建强名称标记。  从开始弃用的[!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)]。  
  
 [StrongNameTokenFromAssemblyEx 函数](../../../../docs/framework/unmanaged-api/strong-naming/strongnametokenfromassemblyex-function.md)  
 从指定的程序集文件中，创建强名称标记并返回公钥。 从开始弃用的[!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)]。  
  
 [StrongNameTokenFromPublicKey 函数](../../../../docs/framework/unmanaged-api/strong-naming/strongnametokenfrompublickey-function.md)  
 获取表示公钥的标记。 从开始弃用的[!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)]。  
  
 [强命名结构](http://msdn.microsoft.com/en-us/4b041a2f-fd12-4b91-aacd-bc3b34a5124d)  
 描述强命名 API 用于管理强名称签名的程序集的非托管的结构...  
  
 [PublicKeyBlob Strong Naming](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md)  
 表示二进制格式公钥/私钥对的公钥。  
  
## <a name="see-also"></a>请参阅  
 [ICLRStrongName 接口](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)  
 [非托管 API 参考](../../../../docs/framework/unmanaged-api/index.md)
