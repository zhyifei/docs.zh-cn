---
title: WCF 安全中的加密灵活性
ms.date: 03/30/2017
ms.assetid: c2c549e5-ac19-40c5-b686-8f67f52b6dbf
author: BrucePerlerMS
ms.openlocfilehash: ebc1b51e2e16f1414f2ed1f4a49a69e26583a17b
ms.sourcegitcommit: 8c28ab17c26bf08abbd004cc37651985c68841b8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/07/2018
ms.locfileid: "48847335"
---
# <a name="cryptographic-agility-in-wcf-security"></a>WCF 安全中的加密灵活性
此示例演示如何在要提供加密的敏捷实现 Windows Communication Foundation (WCF) 客户端和服务中的标准/自定义算法中指定。 该示例由下列项目组成：

 这是实现一个自承载的 WCF 服务的服务`ICalculator`接口，并保护终结点使用 <<!--zz xref:System.ServiceModel.WsHttpBinding --> `xref:System.ServiceModel.WsHttpBinding`> 使用安全会话和可靠会话被禁用。 该服务定义一个自定义 `SecurityAlgorithmSuite` 类，以指定要用于消息安全的加密算法。

 客户端这是身份验证成功后访问该服务 WCFclient。 该客户端调用由 `ICalculator` 接口公开并由服务实现的操作。 该客户端也定义相同的自定义 `SecurityAlgorithmSuite` 类，以指定要用于消息安全的加密算法。

### <a name="to-use-this-sample"></a>使用此示例

1.  在 Visual Studio 2012 中打开 CryptoAgility.sln 解决方案。

2.  按 Ctrl+Shift+B 生成解决方案。

3.  打开[!INCLUDE[fileExplorer](../../../../includes/fileexplorer-md.md)]并导航到 \WCF\Basic\Security\CryptoAgility\Service\bin 目录，并使用管理员特权运行 service.exe 文件，通过右击 service.exe 并选择**以管理员身份运行**。

4.  导航到 \WCF\Basic\Security\CryptoAgility\Client\bin 目录并正常运行 client.exe 文件。

> [!IMPORTANT]
>  您的计算机上可能已安装这些示例。 在继续操作之前，请先检查以下（默认）目录：  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  如果此目录不存在，请转到[Windows Communication Foundation (WCF) 和.NET Framework 4 的 Windows Workflow Foundation (WF) 示例](https://go.microsoft.com/fwlink/?LinkId=150780)若要下载所有 Windows Communication Foundation (WCF) 和[!INCLUDE[wf1](../../../../includes/wf1-md.md)]示例。 此示例位于以下目录：  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Security\CryptoAgility`  
  
## <a name="see-also"></a>请参阅  
 [安全性](../../../../docs/framework/wcf/feature-details/security.md)
