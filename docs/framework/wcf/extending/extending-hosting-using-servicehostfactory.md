---
title: 使用 ServiceHostFactory 扩展宿主
ms.date: 03/30/2017
ms.assetid: bcc5ae1b-21ce-4e0e-a184-17fad74a441e
ms.openlocfilehash: e553fe161ffc5b50850d916cf1cef6b38dd5c1a9
ms.sourcegitcommit: 15109844229ade1c6449f48f3834db1b26907824
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2018
---
# <a name="extending-hosting-using-servicehostfactory"></a><span data-ttu-id="5bf30-102">使用 ServiceHostFactory 扩展宿主</span><span class="sxs-lookup"><span data-stu-id="5bf30-102">Extending Hosting Using ServiceHostFactory</span></span>
<span data-ttu-id="5bf30-103">标准<xref:System.ServiceModel.ServiceHost>用于托管服务中 Windows Communication Foundation (WCF) API 是 WCF 体系结构中的一个扩展点。</span><span class="sxs-lookup"><span data-stu-id="5bf30-103">The standard <xref:System.ServiceModel.ServiceHost> API for hosting services in Windows Communication Foundation (WCF) is an extensibility point in the WCF architecture.</span></span> <span data-ttu-id="5bf30-104">在打开服务之前，用户可以从 <xref:System.ServiceModel.ServiceHost> 派生各自的宿主类，通常是重写 <xref:System.ServiceModel.Channels.CommunicationObject.OnOpening> 以使用 <xref:System.ServiceModel.Description.ServiceDescription> 来以强制方式添加默认终结点或修改行为。</span><span class="sxs-lookup"><span data-stu-id="5bf30-104">Users can derive their own host classes from <xref:System.ServiceModel.ServiceHost>, usually to override <xref:System.ServiceModel.Channels.CommunicationObject.OnOpening> to use <xref:System.ServiceModel.Description.ServiceDescription> to add default endpoints imperatively or modify behaviors, prior to opening the service.</span></span>  
  
 <span data-ttu-id="5bf30-105">在自承载环境中，无需创建自定义 <xref:System.ServiceModel.ServiceHost>，因为您可以编写实例化宿主的代码，然后在实例化宿主后调用宿主上的 <xref:System.ServiceModel.ICommunicationObject.Open>。</span><span class="sxs-lookup"><span data-stu-id="5bf30-105">In the self-host environment, you do not have to create a custom <xref:System.ServiceModel.ServiceHost> because you write the code that instantiates the host and then call <xref:System.ServiceModel.ICommunicationObject.Open> on it after you instantiate it.</span></span> <span data-ttu-id="5bf30-106">在这两个步骤之间，可以执行所需的任何操作。</span><span class="sxs-lookup"><span data-stu-id="5bf30-106">Between those two steps you can do whatever you want.</span></span> <span data-ttu-id="5bf30-107">例如，可以添加新的 <xref:System.ServiceModel.Description.IServiceBehavior>：</span><span class="sxs-lookup"><span data-stu-id="5bf30-107">You could, for example, add a new <xref:System.ServiceModel.Description.IServiceBehavior>:</span></span>  
  
```  
public static void Main()  
{  
   ServiceHost host = new ServiceHost( typeof( MyService ) );  
   host.Description.Add( new MyServiceBehavior() );  
   host.Open();  
  
   ...  
}  
```  
  
 <span data-ttu-id="5bf30-108">此方法不可重用。</span><span class="sxs-lookup"><span data-stu-id="5bf30-108">This approach is not reusable.</span></span> <span data-ttu-id="5bf30-109">操作说明的代码将会编码到宿主程序中（在本例中为 Main() 函数），因此在其他上下文中重用该逻辑很困难。</span><span class="sxs-lookup"><span data-stu-id="5bf30-109">The code that manipulates the description is coded into the host program (in this case, the Main() function), so it is difficult to reuse that logic in other contexts.</span></span> <span data-ttu-id="5bf30-110">还有其他不需要强制性代码的添加 <xref:System.ServiceModel.Description.IServiceBehavior> 的方式。</span><span class="sxs-lookup"><span data-stu-id="5bf30-110">There are also other ways of adding an <xref:System.ServiceModel.Description.IServiceBehavior> that do not require imperative code.</span></span> <span data-ttu-id="5bf30-111">可以从 <xref:System.ServiceModel.ServiceBehaviorAttribute> 派生属性并将其放置在服务实现类型上，或者可以使自定义行为成为可配置的并使用配置以动态方式对其进行组合。</span><span class="sxs-lookup"><span data-stu-id="5bf30-111">You can derive an attribute from <xref:System.ServiceModel.ServiceBehaviorAttribute> and put that on your service implementation type or you can make a custom behavior configurable and compose it dynamically using configuration.</span></span>  
  
 <span data-ttu-id="5bf30-112">但是，对示例稍加变化也可解决此问题。</span><span class="sxs-lookup"><span data-stu-id="5bf30-112">However, a slight variation of the example can also be used to solve this problem.</span></span> <span data-ttu-id="5bf30-113">一个办法是将添加 ServiceBehavior 的代码从 `Main()` 中移动到 <xref:System.ServiceModel.Channels.CommunicationObject.OnOpening%2A> 的自定义派生的 <xref:System.ServiceModel.ServiceHost> 方法中：</span><span class="sxs-lookup"><span data-stu-id="5bf30-113">One approach is to move the code that adds the ServiceBehavior out of `Main()` and into the <xref:System.ServiceModel.Channels.CommunicationObject.OnOpening%2A> method of a custom derivative of <xref:System.ServiceModel.ServiceHost>:</span></span>  
  
```  
public class DerivedHost : ServiceHost  
{  
   public DerivedHost( Type t, params Uri baseAddresses ) :  
      base( t, baseAddresses ) {}  
  
   public override void OnOpening()  
   {  
  this.Description.Add( new MyServiceBehavior() );  
   }  
}  
```  
  
 <span data-ttu-id="5bf30-114">然后，可以使用以下代码来替代 `Main()`：</span><span class="sxs-lookup"><span data-stu-id="5bf30-114">Then, inside of `Main()` you can use:</span></span>  
  
```  
public static void Main()  
{  
   ServiceHost host = new DerivedHost( typeof( MyService ) );  
   host.Open();  
  
   ...  
}  
```  
  
 <span data-ttu-id="5bf30-115">现在您已将自定义逻辑封装到一个全新的抽象中，该抽象可以很容易地在许多不同的宿主可执行文件之间进行重用。</span><span class="sxs-lookup"><span data-stu-id="5bf30-115">Now you have encapsulated the custom logic into a clean abstraction that can be easily reused across many different host executables.</span></span>  
  
 <span data-ttu-id="5bf30-116">如何从 Internet 信息服务 (IIS) 或 Windows 进程激活服务 (WAS) 中使用此自定义 <xref:System.ServiceModel.ServiceHost> 并不是立即就显而易见的。</span><span class="sxs-lookup"><span data-stu-id="5bf30-116">It is not immediately obvious how to use this custom <xref:System.ServiceModel.ServiceHost> from inside of Internet Information Services (IIS) or Windows Process Activation Service (WAS).</span></span> <span data-ttu-id="5bf30-117">这些环境与自承载环境不同，因为宿主环境是代表应用程序实例化 <xref:System.ServiceModel.ServiceHost> 的环境。</span><span class="sxs-lookup"><span data-stu-id="5bf30-117">Those environments are different than the self-host environment, because the hosting environment is the one instantiating the <xref:System.ServiceModel.ServiceHost> on behalf of the application.</span></span> <span data-ttu-id="5bf30-118">IIS 和 WAS 宿主基础结构不清楚有关自定义 <xref:System.ServiceModel.ServiceHost> 派生的任何情况。</span><span class="sxs-lookup"><span data-stu-id="5bf30-118">The IIS and WAS hosting infrastructure does not know anything about your custom <xref:System.ServiceModel.ServiceHost> derivative.</span></span>  
  
 <span data-ttu-id="5bf30-119"><xref:System.ServiceModel.Activation.ServiceHostFactory> 旨在解决从 IIS 或 WAS 中访问自定义 <xref:System.ServiceModel.ServiceHost> 的问题。</span><span class="sxs-lookup"><span data-stu-id="5bf30-119">The <xref:System.ServiceModel.Activation.ServiceHostFactory> was designed to solve this problem of accessing your custom <xref:System.ServiceModel.ServiceHost> from within IIS or WAS.</span></span> <span data-ttu-id="5bf30-120">因为从 <xref:System.ServiceModel.ServiceHost> 派生的自定义宿主是动态配置的并且可能为各种类型，所以宿主环境决从不会直接将其实例化。</span><span class="sxs-lookup"><span data-stu-id="5bf30-120">Because a custom host that is derived from <xref:System.ServiceModel.ServiceHost> is dynamically configured and potentially of various types, the hosting environment never instantiates it directly.</span></span> <span data-ttu-id="5bf30-121">相反，WCF 还使用工厂模式提供宿主环境和服务的具体类型之间的间接层。</span><span class="sxs-lookup"><span data-stu-id="5bf30-121">Instead, WCF uses a factory pattern to provide a layer of indirection between the hosting environment and the concrete type of the service.</span></span> <span data-ttu-id="5bf30-122">除非进行通知，否则它使用返回 <xref:System.ServiceModel.Activation.ServiceHostFactory> 的实例的 <xref:System.ServiceModel.ServiceHost> 的默认实现。</span><span class="sxs-lookup"><span data-stu-id="5bf30-122">Unless you tell it otherwise, it uses a default implementation of <xref:System.ServiceModel.Activation.ServiceHostFactory> that returns an instance of <xref:System.ServiceModel.ServiceHost>.</span></span> <span data-ttu-id="5bf30-123">但你还可以提供自己的工厂返回派生的宿主通过指定工厂实现中的 CLR 类型名称@ServiceHost指令。</span><span class="sxs-lookup"><span data-stu-id="5bf30-123">But you can also provide your own factory that returns your derived host by specifying the CLR type name of your factory implementation in the @ServiceHost directive.</span></span>  
  
 <span data-ttu-id="5bf30-124">对于简单的情形，实现您自己的工厂的练习应该是简单明了的。</span><span class="sxs-lookup"><span data-stu-id="5bf30-124">The intent is that for basic cases, implementing your own factory should be a straight forward exercise.</span></span> <span data-ttu-id="5bf30-125">例如，下面是用于返回派生的 <xref:System.ServiceModel.Activation.ServiceHostFactory> 的自定义 <xref:System.ServiceModel.ServiceHost>：</span><span class="sxs-lookup"><span data-stu-id="5bf30-125">For example, here is a custom <xref:System.ServiceModel.Activation.ServiceHostFactory> that returns a derived <xref:System.ServiceModel.ServiceHost>:</span></span>  
  
```  
public class DerivedFactory : ServiceHostFactory  
{  
   public override ServiceHost CreateServiceHost( Type t, Uri[] baseAddresses )  
   {  
      return new DerivedHost( t, baseAddresses )  
   }  
}  
```  
  
 <span data-ttu-id="5bf30-126">若要使用此工厂，而不是默认工厂，提供中的类型名称@ServiceHost指令，如下所示：</span><span class="sxs-lookup"><span data-stu-id="5bf30-126">To use this factory instead of the default factory, provide the type name in the @ServiceHost directive as follows:</span></span>  
  
```  
<% @ServiceHost Factory="DerivedFactory" Service="MyService" %>  
```  
  
 <span data-ttu-id="5bf30-127">尽管对于从 <xref:System.ServiceModel.ServiceHost> 返回的 <xref:System.ServiceModel.Activation.ServiceHostFactory.CreateServiceHost%2A> 可以执行什么操作没有技术限制，但建议您尽可能使工厂实现简单化。</span><span class="sxs-lookup"><span data-stu-id="5bf30-127">While there is no technical limit on doing what you want to the <xref:System.ServiceModel.ServiceHost> you return from <xref:System.ServiceModel.Activation.ServiceHostFactory.CreateServiceHost%2A>, we suggest that you keep your factory implementations as simple as possible.</span></span> <span data-ttu-id="5bf30-128">如果有大量的自定义逻辑，最好将这些逻辑放入宿主内而不是工厂内，以便可以重用它们。</span><span class="sxs-lookup"><span data-stu-id="5bf30-128">If you have lots of custom logic, it is better to put that logic inside of you host instead of inside the factory so that it can be reusable.</span></span>  
  
 <span data-ttu-id="5bf30-129">应在这里提及另一个承载 API 的层。</span><span class="sxs-lookup"><span data-stu-id="5bf30-129">There is one more layer to the hosting API that should be mentioned here.</span></span> <span data-ttu-id="5bf30-130">WCF 还具有<xref:System.ServiceModel.ServiceHostBase>和<xref:System.ServiceModel.Activation.ServiceHostFactoryBase>，从中<xref:System.ServiceModel.ServiceHost>和<xref:System.ServiceModel.Activation.ServiceHostFactory>分别派生。</span><span class="sxs-lookup"><span data-stu-id="5bf30-130">WCF also has <xref:System.ServiceModel.ServiceHostBase> and <xref:System.ServiceModel.Activation.ServiceHostFactoryBase>, from which <xref:System.ServiceModel.ServiceHost> and <xref:System.ServiceModel.Activation.ServiceHostFactory> respectively derive.</span></span> <span data-ttu-id="5bf30-131">对于您必须通过自己的自定义创建来交换元数据系统的大型组件的更高级方案，存在上述这些特性。</span><span class="sxs-lookup"><span data-stu-id="5bf30-131">Those exist for more advanced scenarios where you must swap out large parts of the metadata system with your own customized creations.</span></span>
