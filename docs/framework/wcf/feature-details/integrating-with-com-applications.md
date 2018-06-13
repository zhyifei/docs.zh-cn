---
title: 与 COM 应用程序集成
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Communication Foundation, COM integration
- COM [WCF], Windows Communication Foundation integration
- WCF, reusing code
- Windows Communication Foundation, reusing code
- COM [WCF]
- WCF, COM integration
ms.assetid: c98bda3e-6779-419e-8e6d-9aa94053026d
ms.openlocfilehash: 292892ef572bd63fff055aeed88073573fadb934
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33491837"
---
# <a name="integrating-with-com-applications"></a>与 COM 应用程序集成
Windows Communication Foundation (WCF) 服务可以直接集成到现有的代码使用 WCF 服务标记。 服务标记可以在众多基于 COM 的开发环境（如 Office VBA、Visual Basic 6.0 或 Visual C++ 6.0）中使用。  
  
## <a name="in-this-section"></a>本节内容  
 [与 COM 应用程序集成的概述](../../../../docs/framework/wcf/feature-details/integrating-with-com-applications-overview.md)  
 对集成过程的主要部分进行概述。  
  
 [如何：注册和配置服务名字对象](../../../../docs/framework/wcf/feature-details/how-to-register-and-configure-a-service-moniker.md)  
 若要使用 COM 应用程序中的 WCF 服务标记，请向 COM 注册所需的特性化的类型和配置所需的绑定配置的 COM 应用程序和标记。  
  
 [如何：使用未注册的 Windows Communication Foundation 服务名字对象](../../../../docs/framework/wcf/feature-details/use-the-wcf-service-moniker-without-registration.md)  
 说明如何以 Web 服务定义语言 (WSDL) 文档的形式或者从 WS-MetadataExchange 终结点获取协定的定义。  
  
 [如何：将服务名字对象用于 WSDL 协定](../../../../docs/framework/wcf/feature-details/how-to-use-a-service-moniker-with-wsdl-contracts.md)  
 描述如何调用一个 WCF 示例使用 WCF WSDL 标记。  
  
 [如何：将服务名字对象与元数据交换协定一起使用](../../../../docs/framework/wcf/feature-details/how-to-use-a-service-moniker-with-metadata-exchange-contracts.md)  
 描述如何调用一个 WCF 示例，使用指定 Mex 终结点的 WCF 标记。  
  
 [如何：指定通道安全凭据](../../../../docs/framework/wcf/feature-details/how-to-specify-channel-security-credentials.md)  
 WCF 服务标记支持`IChannelCredentials`允许使用一系列替换方法来指定通道凭据的接口。  
  
## <a name="reference"></a>参考  
 <xref:System.ServiceModel>  
  
## <a name="see-also"></a>请参阅  
 [与 COM+ 应用程序集成](../../../../docs/framework/wcf/feature-details/integrating-with-com-plus-applications.md)
