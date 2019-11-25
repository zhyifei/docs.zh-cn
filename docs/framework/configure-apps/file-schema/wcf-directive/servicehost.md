---
title: '@ServiceHost'
ms.date: 03/30/2017
ms.assetid: 96ba6967-00f2-422f-9aa7-15de4d33ebf3
ms.openlocfilehash: dd3dd026749ccc299cd922b79dcae8ccbcc722d8
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/12/2019
ms.locfileid: "73968830"
---
# <a name="servicehost"></a><span data-ttu-id="56cca-101">\@ServiceHost</span><span class="sxs-lookup"><span data-stu-id="56cca-101">\@ServiceHost</span></span>
<span data-ttu-id="56cca-102">将用于生成服务主机的工厂与要承载的服务以及访问或编译 .svc 文件中提供的宿主代码所需的其他编程方面相关联。</span><span class="sxs-lookup"><span data-stu-id="56cca-102">Associates the factory used to produce the service host with the service to be hosted and other programming aspects required to access or compile the hosting code provided in the .svc file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="56cca-103">语法</span><span class="sxs-lookup"><span data-stu-id="56cca-103">Syntax</span></span>  
  
```xml  
<% @ServiceHost
Service = "Service, ServiceNamespace"
Factory = "Factory, FactoryNamespace"
Debug = "Debug"
Language = "Language"
CodeBehind = "CodeBehind"
%>
```  
  
## <a name="attributes"></a><span data-ttu-id="56cca-104">特性</span><span class="sxs-lookup"><span data-stu-id="56cca-104">Attributes</span></span>  
  
#### <a name="service"></a><span data-ttu-id="56cca-105">服务</span><span class="sxs-lookup"><span data-stu-id="56cca-105">Service</span></span>  
 <span data-ttu-id="56cca-106">承载的服务的 CLR 类型名称。</span><span class="sxs-lookup"><span data-stu-id="56cca-106">The CLR type name of the service hosted.</span></span> <span data-ttu-id="56cca-107">此名称应为实现一个或多个服务协定的类型的限定名称。</span><span class="sxs-lookup"><span data-stu-id="56cca-107">This should be a qualified name of a type that implements one or more of the service contacts.</span></span>  
  
#### <a name="factory"></a><span data-ttu-id="56cca-108">Factory</span><span class="sxs-lookup"><span data-stu-id="56cca-108">Factory</span></span>  
 <span data-ttu-id="56cca-109">用于实例化服务主机的服务主机工厂的 CLR 类型名称。</span><span class="sxs-lookup"><span data-stu-id="56cca-109">The CLR type name of the service host factory used to instantiate the service host.</span></span> <span data-ttu-id="56cca-110">此属性是可选的。</span><span class="sxs-lookup"><span data-stu-id="56cca-110">This attribute is optional.</span></span> <span data-ttu-id="56cca-111">如果未指定，则使用默认的 <xref:System.ServiceModel.Activation.ServiceHostFactory>，这将返回 <xref:System.ServiceModel.ServiceHost> 的实例。</span><span class="sxs-lookup"><span data-stu-id="56cca-111">If unspecified, the default <xref:System.ServiceModel.Activation.ServiceHostFactory> is used, which returns an instance of <xref:System.ServiceModel.ServiceHost>.</span></span>  
  
#### <a name="debug"></a><span data-ttu-id="56cca-112">调试</span><span class="sxs-lookup"><span data-stu-id="56cca-112">Debug</span></span>  
 <span data-ttu-id="56cca-113">指示是否应用调试符号编译 Windows Communication Foundation （WCF）服务。</span><span class="sxs-lookup"><span data-stu-id="56cca-113">Indicates whether the Windows Communication Foundation (WCF) service should be compiled with debug symbols.</span></span> <span data-ttu-id="56cca-114">`true` 如果 WCF 服务应用调试符号编译，则为; 否则为。否则，`false`。</span><span class="sxs-lookup"><span data-stu-id="56cca-114">`true` if the WCF service should be compiled with debug symbols; otherwise, `false`.</span></span>  
  
#### <a name="language"></a><span data-ttu-id="56cca-115">语言</span><span class="sxs-lookup"><span data-stu-id="56cca-115">Language</span></span>  
 <span data-ttu-id="56cca-116">指定编译文件 (.svc) 中的所有内联代码时使用的语言。</span><span class="sxs-lookup"><span data-stu-id="56cca-116">Specifies the language used when compiling all the inline code within file (.svc).</span></span> <span data-ttu-id="56cca-117">这些值可以表示 .NET 支持的任何语言，包括 C#、VB 和 JS，这三项分别表示 C#、Visual Basic .NET 和 JScript .NET。</span><span class="sxs-lookup"><span data-stu-id="56cca-117">The values can represent any .NET-supported language, including C#, VB, and JS, which refer to C#, Visual Basic .NET, and JScript .NET, respectively.</span></span> <span data-ttu-id="56cca-118">此属性是可选的。</span><span class="sxs-lookup"><span data-stu-id="56cca-118">This attribute is optional.</span></span>  
  
#### <a name="codebehind"></a><span data-ttu-id="56cca-119">CodeBehind</span><span class="sxs-lookup"><span data-stu-id="56cca-119">CodeBehind</span></span>  
 <span data-ttu-id="56cca-120">当实现 XML Web services 的类未驻留在相同的文件中，且尚未编译成程序集并放置在 \Bin 目录中时，指定实现 XML Web services 的源文件。</span><span class="sxs-lookup"><span data-stu-id="56cca-120">Specifies the source file that implements the XML Web service, when the class that implements the XML Web service does not reside in the same file and has not been compiled into an assembly and placed in the \Bin directory.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="56cca-121">备注</span><span class="sxs-lookup"><span data-stu-id="56cca-121">Remarks</span></span>  
 <span data-ttu-id="56cca-122">用于承载服务的 <xref:System.ServiceModel.ServiceHost> 是 Windows Communication Foundation （WCF）编程模型中的一个扩展点。</span><span class="sxs-lookup"><span data-stu-id="56cca-122">The <xref:System.ServiceModel.ServiceHost> used to host the service is a point of extensibility within the Windows Communication Foundation (WCF) programming model.</span></span> <span data-ttu-id="56cca-123">由于 <xref:System.ServiceModel.ServiceHost> 可能属于宿主环境不应直接实例化的多态类型，因此使用工厂模式对其进行实例化。</span><span class="sxs-lookup"><span data-stu-id="56cca-123">A factory pattern is used to instantiate the <xref:System.ServiceModel.ServiceHost> because it is, potentially, a polymorphic type that the hosting environment should not instantiate directly.</span></span>  
  
 <span data-ttu-id="56cca-124">默认实现使用 <xref:System.ServiceModel.Activation.ServiceHostFactory> 创建 <xref:System.ServiceModel.ServiceHost> 的实例。</span><span class="sxs-lookup"><span data-stu-id="56cca-124">The default implementation uses <xref:System.ServiceModel.Activation.ServiceHostFactory> to create an instance of <xref:System.ServiceModel.ServiceHost>.</span></span> <span data-ttu-id="56cca-125">但你可以通过在[\@ServiceHost](servicehost.md)指令中指定工厂实现的 CLR 类型名称来提供自己的工厂（返回派生主机的工厂）。</span><span class="sxs-lookup"><span data-stu-id="56cca-125">But you can provide your own factory (one that returns your derived host) by specifying the CLR type name of your factory implementation in the [\@ServiceHost](servicehost.md) directive.</span></span>  
  
 <span data-ttu-id="56cca-126">若要使用自定义服务主机工厂而不是默认工厂，只需在[@ServiceHost](servicehost.md)指令中提供类型名称，如下所示：</span><span class="sxs-lookup"><span data-stu-id="56cca-126">To use you own custom service host factory instead of the default factory, just provide the type name in the [@ServiceHost](servicehost.md) directive as follows:</span></span>  
  
```xml  
<% @ServiceHost Factory="DerivedFactory" Service="MyService" %>  
```  
  
 <span data-ttu-id="56cca-127">尽可能简化工厂实现。</span><span class="sxs-lookup"><span data-stu-id="56cca-127">Keep the factory implementations as light as possible.</span></span> <span data-ttu-id="56cca-128">如果具有大量的自定义逻辑，则应将这些逻辑放入宿主而不是工厂内，这样可以获得更好的代码重用性。</span><span class="sxs-lookup"><span data-stu-id="56cca-128">If you have lots of custom logic, your code is more reusable if you put that logic inside your host instead of inside the factory.</span></span>  
  
 <span data-ttu-id="56cca-129">例如，若要为 `MyService`启用支持 AJAX 的终结点，请在[@ServiceHost](servicehost.md)指令中指定 `Factory` 属性值的 <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory>，而不是默认 <xref:System.ServiceModel.Activation.ServiceHostFactory>，如以下示例中所示。</span><span class="sxs-lookup"><span data-stu-id="56cca-129">For example, to enable an AJAX-enabled endpoint for `MyService`, specify the <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory> for the value of the `Factory` attribute, instead of the default <xref:System.ServiceModel.Activation.ServiceHostFactory>, in the [@ServiceHost](servicehost.md) directive as shown in the following example.</span></span>  
  
## <a name="example"></a><span data-ttu-id="56cca-130">示例</span><span class="sxs-lookup"><span data-stu-id="56cca-130">Example</span></span>  
  
```xml  
<% @ServiceHost
Service="MyService"  
Language="C#"  
Debug="true"  
Factory="WebScriptServiceHostFactory"  
%>  
```  
  
## <a name="see-also"></a><span data-ttu-id="56cca-131">请参阅</span><span class="sxs-lookup"><span data-stu-id="56cca-131">See also</span></span>

- [<span data-ttu-id="56cca-132">自定义服务主机</span><span class="sxs-lookup"><span data-stu-id="56cca-132">Custom Service Host</span></span>](../../../wcf/samples/custom-service-host.md)
