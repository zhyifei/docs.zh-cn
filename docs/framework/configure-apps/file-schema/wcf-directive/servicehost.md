---
title: '@ServiceHost'
ms.date: 03/30/2017
ms.assetid: 96ba6967-00f2-422f-9aa7-15de4d33ebf3
ms.openlocfilehash: a56fb1bb9395425222347914fe3f4c17f1a451b7
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69920342"
---
# <a name="servicehost"></a>\@ServiceHost
将用于生成服务主机的工厂与要承载的服务以及访问或编译 .svc 文件中提供的宿主代码所需的其他编程方面相关联。  
  
## <a name="syntax"></a>语法  
  
```  
<% @ServiceHost   
Service = "Service, ServiceNamespace"   
Factory = "Factory, FactoryNamespace"  
Debug = "Debug"  
Language = "Language"   
CodeBehind = "CodeBehind"%>  
```  
  
## <a name="attributes"></a>特性  
  
#### <a name="service"></a>服务  
 承载的服务的 CLR 类型名称。 此名称应为实现一个或多个服务协定的类型的限定名称。  
  
#### <a name="factory"></a>Factory  
 用于实例化服务主机的服务主机工厂的 CLR 类型名称。 此属性是可选的。 如果未指定，则使用默认的 <xref:System.ServiceModel.Activation.ServiceHostFactory>，这将返回 <xref:System.ServiceModel.ServiceHost> 的实例。  
  
#### <a name="debug"></a>调试  
 指示是否应用调试符号编译 Windows Communication Foundation (WCF) 服务。 `true`如果应用调试符号编译 WCF 服务, 则为; 否则为。否则为`false`。  
  
#### <a name="language"></a>语言  
 指定编译文件 (.svc) 中的所有内联代码时使用的语言。 这些值可以表示 .NET 支持的任何语言，包括 C#、VB 和 JS，这三项分别表示 C#、Visual Basic .NET 和 JScript .NET。 此属性是可选的。  
  
#### <a name="codebehind"></a>CodeBehind  
 当实现 XML Web services 的类未驻留在相同的文件中，且尚未编译成程序集并放置在 \Bin 目录中时，指定实现 XML Web services 的源文件。  
  
## <a name="remarks"></a>备注  
 <xref:System.ServiceModel.ServiceHost>用于承载服务的是 Windows Communication Foundation (WCF) 编程模型中的一个扩展点。 由于 <xref:System.ServiceModel.ServiceHost> 可能属于宿主环境不应直接实例化的多态类型，因此使用工厂模式对其进行实例化。  
  
 默认实现使用 <xref:System.ServiceModel.Activation.ServiceHostFactory> 创建 <xref:System.ServiceModel.ServiceHost> 的实例。 但你可以通过在[ \@ServiceHost](servicehost.md)指令中指定工厂实现的 CLR 类型名称来提供自己的工厂 (一个返回派生主机的工厂)。  
  
 若要使用自定义服务主机工厂而不是默认工厂, 只需在[@ServiceHost](servicehost.md)指令中提供类型名称, 如下所示:  
  
```xml  
<% @ServiceHost Factory="DerivedFactory" Service="MyService" %>  
```  
  
 尽可能简化工厂实现。 如果具有大量的自定义逻辑，则应将这些逻辑放入宿主而不是工厂内，这样可以获得更好的代码重用性。  
  
 例如, 若要为启用支持 AJAX 的终结点`MyService`, 请在<xref:System.ServiceModel.Activation.WebScriptServiceHostFactory> [@ServiceHost](servicehost.md)指令中指定`Factory`属性值 (而不是默认<xref:System.ServiceModel.Activation.ServiceHostFactory>值), 如下面的示例中所示。  
  
## <a name="example"></a>示例  
  
```  
<% @ServiceHost   
Service="MyService"  
Language="C#"  
Debug="true"  
Factory="WebScriptServiceHostFactory"  
%>  
```  
  
## <a name="see-also"></a>请参阅

- [自定义服务主机](../../../wcf/samples/custom-service-host.md)
