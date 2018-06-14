---
title: 如何：将服务标记与元数据交换协定一起使用
ms.date: 03/30/2017
ms.assetid: c41a07e5-cb9d-45d6-9ea4-34511e227faf
ms.openlocfilehash: 6265860c2e1efb2f74a0243157a223a33889629a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33491245"
---
# <a name="how-to-use-a-service-moniker-with-metadata-exchange-contracts"></a>如何：将服务标记与元数据交换协定一起使用
开发某些新的 WCF 服务之后，你可能决定你想要能够从脚本或 Visual Basic 6.0 应用程序中调用这些服务。 一种方法将生成 WCF 客户端程序集，向 COM 注册程序集，将程序集安装在 GAC 中，然后在 Visual Basic 代码中引用 COM 类型。 分发应用程序时，必须将分发的 WCF 客户端程序集。 然后，用户必须使用 COM 注册 WCF 客户端程序集，并且将该程序集放置在 GAC 中。 WCF COM 互操作还让你可以在相同的服务调用，而不依赖于 WCF 客户端程序集。 WCF 标记使您能够从任何 COM 兼容语言 （Visual Basic、 VBScript、 Visual Basic for Applications (VBA) 和等等） 可通过指定元数据交换 (Mex) 终结点的服务标记用于提取类型的 URI 调用任何 WCF 服务有关服务的信息。 本主题介绍如何调用 WCF 入门示例使用指定 Mex 终结点的 WCF 标记。  
  
> [!NOTE]
>  实际上，从不实例化由 WCF 客户端程序集定义的类型。 该程序集只用于元数据。  
  
### <a name="using-the-service-moniker-with-a-mex-address"></a>使用带有 Mex 地址的服务标记  
  
1.  生成入门示例并使用 Internet Explorer 浏览至其 URL (http://localhost/ServiceModelSamples/Service.svc)以确保服务正在运行。  
  
2.  生成 Visual Basic 脚本或包含以下代码的 Visual Basic 应用程序：  
  
    ```  
    monString = "service:mexaddress=http://localhost/ServiceModelSamples/Service.svc/MEX"  
    monString = monString + ", address=http://localhost/ServiceModelSamples/Service.svc"  
    monString = monString + ", contract=ICalculator, contractNamespace=http://Microsoft.ServiceModel.Samples"  
    monString = monString + ", binding=WSHttpBinding_ICalculator, bindingNamespace=http://Microsoft.ServiceModel.Samples"  
  
    Set calc = GetObject(monString)  
    MsgBox calc.Add(3, 4)  
    ```  
  
3.  运行 Visual Basic 应用程序或脚本。  
  
    > [!NOTE]
    >  您所调用的服务必须公开标记的 Mex 终结点，以便能够从服务中读取元数据。 有关详细信息，请参阅[如何： 使用配置文件服务的发布元数据](../../../../docs/framework/wcf/feature-details/how-to-publish-metadata-for-a-service-using-a-configuration-file.md)。  
  
    > [!NOTE]
    >  如果标记格式不正确，或如果服务不可用，则对 `GetObject` 的调用将返回一个错误，指示“语法无效”。  如果您收到此错误，请确保所使用的标记正确无误且服务可用。  
  
## <a name="see-also"></a>请参阅  
 [如何：使用未注册的 Windows Communication Foundation 服务名字对象](../../../../docs/framework/wcf/feature-details/use-the-wcf-service-moniker-without-registration.md)  
 [如何：将服务名字对象用于 WSDL 协定](../../../../docs/framework/wcf/feature-details/how-to-use-a-service-moniker-with-wsdl-contracts.md)
