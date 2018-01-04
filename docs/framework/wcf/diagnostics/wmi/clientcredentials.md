---
title: ClientCredentials
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 41dffd6b-8f14-4fed-aefb-2a1bb168efb3
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: d6fba00dc98f6b5525e1cb9588ed52bc483a665e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="clientcredentials"></a>ClientCredentials
ClientCredentials  
  
## <a name="syntax"></a>语法  
  
```  
class ClientCredentials : Behavior  
{  
  string ClientCertificate;  
  string HttpDigest;  
  string IssuedToken;  
  string Peer;  
  string ServiceCertificate;  
  boolean SupportInteractive;  
  string UserName;  
  string Windows;  
};  
```  
  
## <a name="methods"></a>方法  
 ClientCredentials 类未定义任何方法。  
  
## <a name="properties"></a>属性  
 ClientCredentials 类具有以下属性：  
  
### <a name="clientcertificate"></a>ClientCertificate  
 数据类型：String  
  
 访问类型：只读  
  
 客户端用来向服务验证身份的 X.509 证书。  
  
### <a name="httpdigest"></a>HttpDigest  
 数据类型：String  
  
 访问类型：只读  
  
 当前 Http Digest 凭据。  
  
### <a name="issuedtoken"></a>IssuedToken  
 数据类型：String  
  
 访问类型：只读  
  
 用于联系本地安全令牌服务的终结点地址和绑定。  
  
### <a name="peer"></a>对等  
 数据类型：String  
  
 访问类型：只读  
  
 对等节点用来向网格中的其他节点验证其自身身份的凭据。  
  
### <a name="servicecertificate"></a>ServiceCertificate  
 数据类型：String  
  
 访问类型：只读  
  
 服务的 X.509 证书。  
  
### <a name="supportinteractive"></a>SupportInteractive  
 数据类型：Boolean  
  
 访问类型：只读  
  
 一个布尔值，指定凭据是否支持交互式协商。  
  
### <a name="username"></a>UserName  
 数据类型：String  
  
 访问类型：只读  
  
 客户端用来向服务验证其自身身份的用户名和密码。  
  
### <a name="windows"></a>Windows  
 数据类型：String  
  
 访问类型：只读  
  
 客户端用来向服务验证其自身身份的 Windows 凭据。  
  
## <a name="requirements"></a>惠?  
  
|MOF|已在 Servicemodel.mof 中声明。|  
|---------|-----------------------------------|  
|命名空间|已在 root\ServiceModel 中定义|  
  
## <a name="see-also"></a>请参阅  
 <xref:System.ServiceModel.Description.ClientCredentials>
