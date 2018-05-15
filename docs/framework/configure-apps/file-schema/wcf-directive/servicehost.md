---
title: '@ServiceHost'
ms.date: 03/30/2017
ms.assetid: 96ba6967-00f2-422f-9aa7-15de4d33ebf3
ms.openlocfilehash: f81c71746b6b59a51ee825b44c9e6d9f93eb5fbd
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
---
# <a name="servicehost"></a>@ServiceHost
<span data-ttu-id="d1214-101">将用于生成服务主机的工厂与要承载的服务以及访问或编译 .svc 文件中提供的主机代码所需的其他编程方面相关联。</span><span class="sxs-lookup"><span data-stu-id="d1214-101">Associates the factory used to produce the service host with the service to be hosted and other programming aspects required to access or compile the hosting code provided in the .svc file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d1214-102">语法</span><span class="sxs-lookup"><span data-stu-id="d1214-102">Syntax</span></span>  
  
```  
<% @ServiceHost   
Service = "Service, ServiceNamespace"   
Factory = "Factory, FactoryNamespace"  
Debug = "Debug"  
Language = "Language"   
CodeBehind = "CodeBehind"%>  
```  
  
## <a name="attributes"></a><span data-ttu-id="d1214-103">特性</span><span class="sxs-lookup"><span data-stu-id="d1214-103">Attributes</span></span>  
  
#### <a name="service"></a><span data-ttu-id="d1214-104">服务</span><span class="sxs-lookup"><span data-stu-id="d1214-104">Service</span></span>  
 <span data-ttu-id="d1214-105">承载的服务的 CLR 类型名称。</span><span class="sxs-lookup"><span data-stu-id="d1214-105">The CLR type name of the service hosted.</span></span> <span data-ttu-id="d1214-106">此名称应为实现一个或多个服务协定的类型的限定名称。</span><span class="sxs-lookup"><span data-stu-id="d1214-106">This should be a qualified name of a type that implements one or more of the service contacts.</span></span>  
  
#### <a name="factory"></a><span data-ttu-id="d1214-107">Factory</span><span class="sxs-lookup"><span data-stu-id="d1214-107">Factory</span></span>  
 <span data-ttu-id="d1214-108">用于实例化服务主机的服务主机工厂的 CLR 类型名称。</span><span class="sxs-lookup"><span data-stu-id="d1214-108">The CLR type name of the service host factory used to instantiate the service host.</span></span> <span data-ttu-id="d1214-109">此属性是可选的。</span><span class="sxs-lookup"><span data-stu-id="d1214-109">This attribute is optional.</span></span> <span data-ttu-id="d1214-110">如果未指定，则使用默认的 <xref:System.ServiceModel.Activation.ServiceHostFactory>，这将返回 <xref:System.ServiceModel.ServiceHost> 的实例。</span><span class="sxs-lookup"><span data-stu-id="d1214-110">If unspecified, the default <xref:System.ServiceModel.Activation.ServiceHostFactory> is used, which returns an instance of <xref:System.ServiceModel.ServiceHost>.</span></span>  
  
#### <a name="debug"></a><span data-ttu-id="d1214-111">调试</span><span class="sxs-lookup"><span data-stu-id="d1214-111">Debug</span></span>  
 <span data-ttu-id="d1214-112">指示是否应使用调试符号编译的 Windows Communication Foundation (WCF) 服务。</span><span class="sxs-lookup"><span data-stu-id="d1214-112">Indicates whether the Windows Communication Foundation (WCF) service should be compiled with debug symbols.</span></span> <span data-ttu-id="d1214-113">如果应使用调试符号编译 `true` 服务，则为 [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)]；否则为 `false`。</span><span class="sxs-lookup"><span data-stu-id="d1214-113">`true` if the [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] service should be compiled with debug symbols; otherwise, `false`.</span></span>  
  
#### <a name="language"></a><span data-ttu-id="d1214-114">语言</span><span class="sxs-lookup"><span data-stu-id="d1214-114">Language</span></span>  
 <span data-ttu-id="d1214-115">指定编译文件 (.svc) 中的所有内联代码时使用的语言。</span><span class="sxs-lookup"><span data-stu-id="d1214-115">Specifies the language used when compiling all the inline code within file (.svc).</span></span> <span data-ttu-id="d1214-116">这些值可以表示 .NET 支持的任何语言，包括 C#、VB 和 JS，这三项分别表示 C#、Visual Basic .NET 和 JScript .NET。</span><span class="sxs-lookup"><span data-stu-id="d1214-116">The values can represent any .NET-supported language, including C#, VB, and JS, which refer to C#, Visual Basic .NET, and JScript .NET, respectively.</span></span> <span data-ttu-id="d1214-117">此属性是可选的。</span><span class="sxs-lookup"><span data-stu-id="d1214-117">This attribute is optional.</span></span>  
  
#### <a name="codebehind"></a><span data-ttu-id="d1214-118">CodeBehind</span><span class="sxs-lookup"><span data-stu-id="d1214-118">CodeBehind</span></span>  
 <span data-ttu-id="d1214-119">当实现 XML Web services 的类未驻留在相同的文件中，且尚未编译成程序集并放置在 \Bin 目录中时，指定实现 XML Web services 的源文件。</span><span class="sxs-lookup"><span data-stu-id="d1214-119">Specifies the source file that implements the XML Web service, when the class that implements the XML Web service does not reside in the same file and has not been compiled into an assembly and placed in the \Bin directory.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d1214-120">备注</span><span class="sxs-lookup"><span data-stu-id="d1214-120">Remarks</span></span>  
 <span data-ttu-id="d1214-121"><xref:System.ServiceModel.ServiceHost>用于承载服务是一个 Windows Communication Foundation (WCF) 编程模型中的可扩展点。</span><span class="sxs-lookup"><span data-stu-id="d1214-121">The <xref:System.ServiceModel.ServiceHost> used to host the service is a point of extensibility within the Windows Communication Foundation (WCF) programming model.</span></span> <span data-ttu-id="d1214-122">由于 <xref:System.ServiceModel.ServiceHost> 可能属于宿主环境不应直接实例化的多态类型，因此使用工厂模式对其进行实例化。</span><span class="sxs-lookup"><span data-stu-id="d1214-122">A factory pattern is used to instantiate the <xref:System.ServiceModel.ServiceHost> because it is, potentially, a polymorphic type that the hosting environment should not instantiate directly.</span></span>  
  
 <span data-ttu-id="d1214-123">默认实现使用 <xref:System.ServiceModel.Activation.ServiceHostFactory> 创建 <xref:System.ServiceModel.ServiceHost> 的实例。</span><span class="sxs-lookup"><span data-stu-id="d1214-123">The default implementation uses <xref:System.ServiceModel.Activation.ServiceHostFactory> to create an instance of <xref:System.ServiceModel.ServiceHost>.</span></span> <span data-ttu-id="d1214-124">但你可以通过指定工厂实现中的 CLR 类型名称提供您自己的工厂 （一个用于返回派生的宿主） [ @ServiceHost ](../../../../../docs/framework/configure-apps/file-schema/wcf-directive/servicehost.md)指令。</span><span class="sxs-lookup"><span data-stu-id="d1214-124">But you can provide your own factory (one that returns your derived host) by specifying the CLR type name of your factory implementation in the [@ServiceHost](../../../../../docs/framework/configure-apps/file-schema/wcf-directive/servicehost.md) directive.</span></span>  
  
 <span data-ttu-id="d1214-125">若要使用你自己的自定义服务主机工厂而不是默认工厂，只需提供中的类型名称[ @ServiceHost ](../../../../../docs/framework/configure-apps/file-schema/wcf-directive/servicehost.md)指令，如下所示：</span><span class="sxs-lookup"><span data-stu-id="d1214-125">To use you own custom service host factory instead of the default factory, just provide the type name in the [@ServiceHost](../../../../../docs/framework/configure-apps/file-schema/wcf-directive/servicehost.md) directive as follows:</span></span>  
  
```xml  
<% @ServiceHost Factory="DerivedFactory" Service="MyService" %>  
```  
  
 <span data-ttu-id="d1214-126">尽可能简化工厂实现。</span><span class="sxs-lookup"><span data-stu-id="d1214-126">Keep the factory implementations as light as possible.</span></span> <span data-ttu-id="d1214-127">如果具有大量的自定义逻辑，则应将这些逻辑放入宿主而不是工厂内，这样可以获得更好的代码重用性。</span><span class="sxs-lookup"><span data-stu-id="d1214-127">If you have lots of custom logic, your code is more reusable if you put that logic inside your host instead of inside the factory.</span></span>  
  
 <span data-ttu-id="d1214-128">例如，若要启用 ajax 的终结点为`MyService`，指定<xref:System.ServiceModel.Activation.WebScriptServiceHostFactory>的值的`Factory`属性，而不是默认值<xref:System.ServiceModel.Activation.ServiceHostFactory>中[ @ServiceHost ](../../../../../docs/framework/configure-apps/file-schema/wcf-directive/servicehost.md)作为指令下面的示例所示。</span><span class="sxs-lookup"><span data-stu-id="d1214-128">For example, to enable an AJAX-enabled endpoint for `MyService`, specify the <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory> for the value of the `Factory` attribute, instead of the default <xref:System.ServiceModel.Activation.ServiceHostFactory>, in the [@ServiceHost](../../../../../docs/framework/configure-apps/file-schema/wcf-directive/servicehost.md) directive as shown in the following example.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d1214-129">示例</span><span class="sxs-lookup"><span data-stu-id="d1214-129">Example</span></span>  
  
```  
<% @ServiceHost   
Service="MyService"  
Language="C#"  
Debug="true"  
Factory="WebScriptServiceHostFactory"  
%>  
```  
  
## <a name="see-also"></a><span data-ttu-id="d1214-130">请参阅</span><span class="sxs-lookup"><span data-stu-id="d1214-130">See Also</span></span>  
 [<span data-ttu-id="d1214-131">自定义服务主机</span><span class="sxs-lookup"><span data-stu-id="d1214-131">Custom Service Host</span></span>](../../../../../docs/framework/wcf/samples/custom-service-host.md)
