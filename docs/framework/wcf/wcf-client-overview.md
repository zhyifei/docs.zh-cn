---
title: WCF 客户端概述
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- clients [WCF], architecture
ms.assetid: f60d9bc5-8ade-4471-8ecf-5a07a936c82d
caps.latest.revision: 17
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 7f083ea44b9bdbd9bf85d65c42d663d87af8d812
ms.sourcegitcommit: 94d33cadc5ff81d2ac389bf5f26422c227832052
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/30/2018
---
# <a name="wcf-client-overview"></a>WCF 客户端概述
本节描述客户端应用程序可以做什么，如何配置、创建和使用 [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] 客户端，以及如何保护客户端应用程序。  
  
## <a name="using-wcf-client-objects"></a>使用 WCF 客户端对象  
 客户端应用程序是使用 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 客户端与其他应用程序通信的托管应用程序。 若要为 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 服务创建一个客户端应用程序，则需要执行下列步骤：  
  
1.  获取服务终结点的服务协定、绑定以及地址信息。  
  
2.  使用该信息创建 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 客户端。  
  
3.  调用操作。  
  
4.  关闭该 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 客户端对象。  
  
 以下部分将讨论上述这些步骤，并简单介绍以下问题：  
  
-   处理错误。  
  
-   配置和保护客户端。  
  
-   为双工服务创建回调对象。  
  
-   异步调用服务。  
  
-   使用客户端通道调用服务。  
  
## <a name="obtain-the-service-contract-bindings-and-addresses"></a>获取服务协定、绑定和地址  
 在 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 中，服务和客户端使用托管属性、接口和方法对协定进行建模。 若要连接客户端应用程序中的服务，则需要获取该服务协定的类型信息。 通常情况下，你执行此操作通过使用[ServiceModel 元数据实用工具 (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)，该服务，从下载元数据将其转换为托管的源代码文件中您选择的语言，并创建一个客户端可用于配置的应用程序配置文件你[!INCLUDE[indigo2](../../../includes/indigo2-md.md)]客户端对象。 例如，如果您准备创建一个 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 客户端对象来调用 `MyCalculatorService`，并且您知道该服务的元数据已在 `http://computerName/MyCalculatorService/Service.svc?wsdl` 中发布，则下面的代码示例演示如何使用 Svcutil.exe 获取一个包含托管代码中的服务协定的 `ClientCode.vb` 文件。  
  
```  
svcutil /language:vb /out:ClientCode.vb /config:app.config http://computerName/MyCalculatorService/Service.svc?wsdl  
```  
  
 您可以将此协定代码编译为客户端应用程序或另一个程序集，然后，客户端应用程序可以使用该程序集创建一个 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 客户端对象。 可以使用配置文件配置客户端对象以与服务正确连接。  
  
 有关此过程的示例，请参阅[如何： 创建客户端](../../../docs/framework/wcf/how-to-create-a-wcf-client.md)。 有关协定的更完整信息，请参阅[协定](../../../docs/framework/wcf/feature-details/contracts.md)。  
  
## <a name="create-a-wcf-client-object"></a>创建一个 WCF 客户端对象  
 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 客户端是表示某个 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 服务的一个本地对象，客户端可以使用这种表示形式与远程服务进行通信。 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 客户端类型可实现目标服务协定，因此在您创建一个服务协定并配置它之后，就可以直接使用该客户端对象调用服务操作。 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]运行时将为方法调入消息、 将它们发送到服务，侦听回复，并返回到这些值[!INCLUDE[indigo2](../../../includes/indigo2-md.md)]用作返回值的客户端对象或`out`或`ref`参数。  
  
 您还可以使用 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 客户端通道对象连接和使用服务。 有关详细信息，请参阅[WCF 客户端体系结构](../../../docs/framework/wcf/feature-details/client-architecture.md)。  
  
#### <a name="creating-a-new-wcf-object"></a>创建一个新的 WCF 对象  
 为了演示如何使用 <xref:System.ServiceModel.ClientBase%601> 类，现假设已从服务应用程序生成了下面的简单服务协定。  
  
> [!NOTE]
>  如果你使用 Visual Studio 来创建你[!INCLUDE[indigo2](../../../includes/indigo2-md.md)]客户端，对象将自动加载到对象浏览器添加到你的项目的服务引用时。  
  
 [!code-csharp[C_GeneratedCodeFiles#12](../../../samples/snippets/csharp/VS_Snippets_CFX/c_generatedcodefiles/cs/proxycode.cs#12)]  
  
 如果你不使用 Visual Studio，检查生成的协定代码以查找扩展的类型<xref:System.ServiceModel.ClientBase%601>以及服务协定接口`ISampleService`。 在这种情况下，该类型看上去类似下列代码：  
  
 [!code-csharp[C_GeneratedCodeFiles#14](../../../samples/snippets/csharp/VS_Snippets_CFX/c_generatedcodefiles/cs/proxycode.cs#14)]  
  
 可以通过使用其中一个构造函数将此类创建为一个本地对象，并对该本地对象进行配置，然后使用它连接到 `ISampleService` 类型的服务。  
  
 建议您首先创建 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 客户端对象，然后使用该对象并在一个单独的 try/catch 块内将它关闭。 不应使用`using`语句 (`Using`在 Visual Basic 中) 因为它可以屏蔽处于某些失败模式的异常。 有关详细信息，请参阅以下部分，以及[避免问题与 Using 语句](../../../docs/framework/wcf/samples/avoiding-problems-with-the-using-statement.md)。  
  
### <a name="contracts-bindings-and-addresses"></a>协定、绑定和地址  
 在可以创建 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 客户端对象之前，必须配置客户端对象。 具体而言，它必须有一个服务*终结点*使用。 终结点由服务协定、绑定和地址组成。 (有关终结点的详细信息，请参阅[终结点： 地址、 绑定和协定](../../../docs/framework/wcf/feature-details/endpoints-addresses-bindings-and-contracts.md)。)通常情况下，此信息是否位于[\<终结点 >](../../../docs/framework/configure-apps/file-schema/wcf/endpoint-of-client.md)客户端应用程序配置文件，例如 Svcutil.exe 工具生成，并创建你的客户端时自动加载中的元素对象。 两种 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 客户端类型都具有使您能够以编程方式指定此信息的重载。  
  
 例如，上述示例中所使用的 `ISampleService` 的生成的配置文件包含以下终结点信息。  
  
 [!code-xml[C_GeneratedCodeFiles#19](../../../samples/snippets/csharp/VS_Snippets_CFX/c_generatedcodefiles/common/client.exe.config#19)]  
  
 此配置文件在 `<client>` 元素中指定目标终结点。 有关使用多个目标终结点的详细信息，请参阅<xref:System.ServiceModel.ClientBase%601.%23ctor%2A?displayProperty=nameWithType>或<xref:System.ServiceModel.ChannelFactory%601.%23ctor%2A?displayProperty=nameWithType>构造函数。  
  
## <a name="calling-operations"></a>调用操作  
 创建并配置了客户端对象后，请创建一个 try/catch 块，如果该对象是本地对象，则以相同的方式调用操作，然后关闭 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 客户端对象。 当客户端应用程序调用第一个操作时，[!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 将自动打开基础通道，并在回收对象时关闭基础通道。 （或者，还可以在调用其他操作之前或之后显式打开和关闭该通道。）  
  
 例如，如果您具有以下服务协定：  
  
```csharp  
namespace Microsoft.ServiceModel.Samples  
{  
    using System;  
    using System.ServiceModel;  
  
    [ServiceContract(Namespace = "http://Microsoft.ServiceModel.Samples")]  
    public interface ICalculator  
   {  
        [OperationContract]  
        double Add(double n1, double n2);  
        [OperationContract]  
        double Subtract(double n1, double n2);  
        [OperationContract]  
        double Multiply(double n1, double n2);  
        [OperationContract]  
        double Divide(double n1, double n2);  
    }  
}  
```  
  
```vb  
Namespace Microsoft.ServiceModel.Samples  
  
    Imports System  
    Imports System.ServiceModel  
  
    <ServiceContract(Namespace:= _  
    "http://Microsoft.ServiceModel.Samples")> _   
   Public Interface ICalculator  
        <OperationContract> _   
        Function Add(n1 As Double, n2 As Double) As Double  
        <OperationContract> _   
        Function Subtract(n1 As Double, n2 As Double) As Double  
        <OperationContract> _   
        Function Multiply(n1 As Double, n2 As Double) As Double  
        <OperationContract> _   
     Function Divide(n1 As Double, n2 As Double) As Double  
End Interface  
```  
  
 您可以通过创建一个 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 客户端对象并调用其方法来调用操作，如以下代码示例所示。 请注意，打开、调用和关闭 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 客户端对象发生在一个 try/catch 块内。 有关详细信息，请参阅[使用 WCF 客户端访问服务](../../../docs/framework/wcf/feature-details/accessing-services-using-a-client.md)和[避免问题与 Using 语句](../../../docs/framework/wcf/samples/avoiding-problems-with-the-using-statement.md)。  
  
 [!code-csharp[C_GeneratedCodeFiles#20](../../../samples/snippets/csharp/VS_Snippets_CFX/c_generatedcodefiles/cs/proxycode.cs#20)]  
  
## <a name="handling-errors"></a>处理错误  
 当打开基础客户端通道（无论是通过显式打开还是通过调用操作自动打开）、使用客户端或通道对象调用操作，或关闭基础客户端通道时，都会在客户端应用程序中出现异常。 除了由操作返回的 SOAP 错误导致引发的任何 <xref:System.TimeoutException?displayProperty=nameWithType> 对象外，建议您至少将应用程序设置为能够处理可能的 <xref:System.ServiceModel.CommunicationException?displayProperty=nameWithType> 和 <xref:System.ServiceModel.FaultException?displayProperty=nameWithType> 异常。 操作协定中指定的 SOAP 错误将作为 <xref:System.ServiceModel.FaultException%601?displayProperty=nameWithType> 在客户端应用程序中引发，此异常中的类型参数为 SOAP 错误的详细信息类型。 有关客户端应用程序中处理错误条件的详细信息，请参阅[发送和接收错误](../../../docs/framework/wcf/sending-and-receiving-faults.md)。 有关完整的示例演示如何处理客户端中的错误，请参阅[预期异常](../../../docs/framework/wcf/samples/expected-exceptions.md)。  
  
## <a name="configuring-and-securing-clients"></a>配置和保护客户端  
 若要配置客户端，请首先为客户端或通道对象加载目标终结点信息，通常是从配置文件中加载该信息，但是也可以使用客户端构造函数和属性以编程方式加载。 但是，若要启用特定的客户端行为或实施一些安全方案还需要执行其他配置步骤。  
  
 例如，服务协定的安全要求已在服务协定接口中声明，并且如果 Svcutil.exe 已创建了一个配置文件，则该文件通常会包含一个能够支持服务安全要求的绑定。 但是在某些情况中，可能需要更多的安全配置，例如配置客户端凭据。 有关安全配置的完整信息[!INCLUDE[indigo2](../../../includes/indigo2-md.md)]客户端，请参阅[保护客户端](../../../docs/framework/wcf/securing-clients.md)。  
  
 此外，在客户端应用程序中还可以启用一些自定义修改，例如自定义运行时行为。 有关如何配置自定义客户端行为的详细信息，请参阅[配置客户端行为](../../../docs/framework/wcf/configuring-client-behaviors.md)。  
  
## <a name="creating-callback-objects-for-duplex-services"></a>为双工服务创建回调对象  
 双工服务指定一个回调协定，客户端应用程序必须实现该协定以便提供一个该服务能够根据协定要求调用的回调对象。 虽然回调对象不是完整的服务（例如，您无法使用回调对象启动一个通道），但是为了实现和配置，这些回调对象可以被视为一种服务。  
  
 双工服务的客户端必须：  
  
-   实现一个回调协定类。  
  
-   创建回调协定实现类的一个实例，并使用该实例创建传递给 <xref:System.ServiceModel.InstanceContext?displayProperty=nameWithType> 客户端构造函数的 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 对象。  
  
-   调用操作并处理操作回调。  
  
 双工 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 客户端对象除了会公开支持回调所必需的功能（包括回调服务的配置）以外，其他的功能和它们的非双工对应项相同。  
  
 例如，可以通过使用回调类的 <xref:System.ServiceModel.CallbackBehaviorAttribute?displayProperty=nameWithType> 属性 (Attribute) 的属性 (Property)，控制回调对象运行时行为的各个方面。 另一个示例是使用 <xref:System.ServiceModel.Description.CallbackDebugBehavior?displayProperty=nameWithType> 类将异常信息返回给调用回调对象的服务。 有关详细信息，请参阅[双工服务](../../../docs/framework/wcf/feature-details/duplex-services.md)。 有关完整示例，请参阅[双工](../../../docs/framework/wcf/samples/duplex.md)。  
  
 在运行 Internet 信息服务 (IIS) 5.1 的 Windows XP 计算机上，双工客户端必须使用 <xref:System.ServiceModel.WSDualHttpBinding?displayProperty=nameWithType> 类指定一个客户端基址，否则会引发异常。 下面的代码示例演示如何在代码中执行此操作。  
  
 [!code-csharp[S_DualHttp#8](../../../samples/snippets/csharp/VS_Snippets_CFX/s_dualhttp/cs/program.cs#8)]
 [!code-vb[S_DualHttp#8](../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_dualhttp/vb/module1.vb#8)]  
  
 下面的代码演示如何在配置文件中执行此操作。  
  
 [!code-csharp[S_DualHttp#134](../../../samples/snippets/csharp/VS_Snippets_CFX/s_dualhttp/cs/program.cs#134)]  
  
## <a name="calling-services-asynchronously"></a>异步调用服务  
 如何调用操作完全取决于客户端开发人员。 这是因为当在托管代码中表示组成操作的消息时，这些消息可以映射到同步或异步方法中。 因此，如果想要生成异步调用操作的客户端，则可以使用 Svcutil.exe 通过 `/async` 选项生成异步客户端代码。 有关详细信息，请参阅[如何： 以异步方式调用服务操作](../../../docs/framework/wcf/feature-details/how-to-call-wcf-service-operations-asynchronously.md)。  
  
## <a name="calling-services-using-wcf-client-channels"></a>使用 WCF 客户端通道调用服务  
 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 客户端类型扩展 <xref:System.ServiceModel.ClientBase%601>，而其自身派生自 <xref:System.ServiceModel.IClientChannel?displayProperty=nameWithType> 接口，从而可以公开基础通道系统。 可以同时使用目标服务协定和 <xref:System.ServiceModel.ChannelFactory%601?displayProperty=nameWithType> 类来调用服务。 有关详细信息，请参阅[WCF 客户端体系结构](../../../docs/framework/wcf/feature-details/client-architecture.md)。  
  
## <a name="see-also"></a>请参阅  
 <xref:System.ServiceModel.ClientBase%601?displayProperty=nameWithType>  
 <xref:System.ServiceModel.ChannelFactory%601?displayProperty=nameWithType>
