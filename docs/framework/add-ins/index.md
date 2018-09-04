---
title: 外接程序和扩展性
ms.date: 03/30/2017
helpviewer_keywords:
- extensibility [.NET Framework], add-ins
- add-ins [.NET Framework]
- add-ins [.NET Framework], about
- hosts [.NET Framework], compared to add-ins
- .NET Framework, add-ins
- add-in pipeline [.NET Framework], about
- add-ins [.NET Framework], compared to hosts
- .NET Framework, extensibility
- versioning [.NET Framework], add-ins
ms.assetid: 8dd45b02-7218-40f9-857d-40d7b98b850b
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: eb2485f2ecf0426360dba80d443500a92b5a7af6
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/04/2018
ms.locfileid: "43510049"
---
# <a name="add-ins-and-extensibility"></a><span data-ttu-id="dc9f0-102">外接程序和扩展性</span><span class="sxs-lookup"><span data-stu-id="dc9f0-102">Add-ins and Extensibility</span></span>
<a name="top"></a> <span data-ttu-id="dc9f0-103">外接程序为主机应用程序提供扩展功能或服务。</span><span class="sxs-lookup"><span data-stu-id="dc9f0-103">Add-ins provide extended features or services for a host application.</span></span> <span data-ttu-id="dc9f0-104">[!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] 提供了一个编程模型，开发人员可利用此模型来开发外接程序并在其主机应用程序中激活。</span><span class="sxs-lookup"><span data-stu-id="dc9f0-104">The [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] provides a programming model that developers can use to develop add-ins and activate them in their host application.</span></span> <span data-ttu-id="dc9f0-105">该模型通过在主机与外接程序之间构造通信管道来实现此功能。</span><span class="sxs-lookup"><span data-stu-id="dc9f0-105">The model achieves this by constructing a communication pipeline between the host and the add-in.</span></span> <span data-ttu-id="dc9f0-106">该模型通过使用 <xref:System.AddIn>、 <xref:System.AddIn.Hosting>、 <xref:System.AddIn.Pipeline>和 <xref:System.AddIn.Contract> 命名空间中的类实现。</span><span class="sxs-lookup"><span data-stu-id="dc9f0-106">The model is implemented by using the types in the <xref:System.AddIn>, <xref:System.AddIn.Hosting>, <xref:System.AddIn.Pipeline>, and <xref:System.AddIn.Contract> namespaces.</span></span>  
  
 <span data-ttu-id="dc9f0-107">本概述包含以下几节：</span><span class="sxs-lookup"><span data-stu-id="dc9f0-107">This overview contains the following sections:</span></span>  
  
-   [<span data-ttu-id="dc9f0-108">外接程序模型</span><span class="sxs-lookup"><span data-stu-id="dc9f0-108">Add-in Model</span></span>](#addin_model)  
  
-   [<span data-ttu-id="dc9f0-109">区分外接程序和主机</span><span class="sxs-lookup"><span data-stu-id="dc9f0-109">Distinguishing Between Add-ins and Hosts</span></span>](#distinguishing_between_addins_and_hosts)  
  
-   [<span data-ttu-id="dc9f0-110">相关主题</span><span class="sxs-lookup"><span data-stu-id="dc9f0-110">Related Topics</span></span>](#related_topics)  
  
-   [<span data-ttu-id="dc9f0-111">引用</span><span class="sxs-lookup"><span data-stu-id="dc9f0-111">Reference</span></span>](#reference)  
  
> [!NOTE]
>  <span data-ttu-id="dc9f0-112">您可以找到其他示例代码和客户工具技术预览生成外接程序管道，用于在[CodePlex 上的托管扩展性和外接程序框架网站](https://go.microsoft.com/fwlink/?LinkId=121190)。</span><span class="sxs-lookup"><span data-stu-id="dc9f0-112">You can find additional sample code, and customer technology previews of tools for building add-in pipelines, at the [Managed Extensibility and Add-In Framework site on CodePlex](https://go.microsoft.com/fwlink/?LinkId=121190).</span></span>  
  
<a name="addin_model"></a>   
## <a name="add-in-model"></a><span data-ttu-id="dc9f0-113">外接程序模型</span><span class="sxs-lookup"><span data-stu-id="dc9f0-113">Add-in Model</span></span>  
 <span data-ttu-id="dc9f0-114">外接程序模型包括组成外接程序管道（也称为通信管道）的一系列段，管道实现外接程序与主机之间的所有通信。</span><span class="sxs-lookup"><span data-stu-id="dc9f0-114">The add-in model consists of a series of segments that make up the add-in pipeline (also known as the communication pipeline), that is responsible for all communication between the add-in and the host.</span></span> <span data-ttu-id="dc9f0-115">管道是使外接程序与主机实现数据交换的段的对称通信模型。</span><span class="sxs-lookup"><span data-stu-id="dc9f0-115">The pipeline is a symmetrical communication model of segments that exchange data between an add-in and its host.</span></span> <span data-ttu-id="dc9f0-116">在主机与外接程序之间开发这些段可提供实现外接程序版本控制和隔离所需的抽象层。</span><span class="sxs-lookup"><span data-stu-id="dc9f0-116">Developing these segments between the host and the add-in provides the required layers of abstraction that support versioning and isolation of the add-in.</span></span>  
  
 <span data-ttu-id="dc9f0-117">下图显示外接程序管道。</span><span class="sxs-lookup"><span data-stu-id="dc9f0-117">The following illustration shows the pipeline.</span></span>  
  
 <span data-ttu-id="dc9f0-118">![添加&#45;管道模型中。](../../../docs/framework/add-ins/media/addin1.png "AddIn1")</span><span class="sxs-lookup"><span data-stu-id="dc9f0-118">![Add&#45;in pipeline model.](../../../docs/framework/add-ins/media/addin1.png "AddIn1")</span></span>  
<span data-ttu-id="dc9f0-119">外接程序管道</span><span class="sxs-lookup"><span data-stu-id="dc9f0-119">Add-in pipeline</span></span>  
  
 <span data-ttu-id="dc9f0-120">这些段的程序集不需要处于同一个应用程序域。</span><span class="sxs-lookup"><span data-stu-id="dc9f0-120">The assemblies for these segments are not required to be in the same application domain.</span></span> <span data-ttu-id="dc9f0-121">可以将外接程序加载至其自己的新应用程序域、现有应用程序域，甚至主机的应用程序域。</span><span class="sxs-lookup"><span data-stu-id="dc9f0-121">You can load an add-in into its own new application domain, into an existing application domain, or even into the host's application domain.</span></span> <span data-ttu-id="dc9f0-122">可以将多个外接程序加载到同一个应用程序域，这样外接程序便可以共享资源和安全性上下文。</span><span class="sxs-lookup"><span data-stu-id="dc9f0-122">You can load multiple add-ins into the same application domain, which enables the add-ins to share resources and security contexts.</span></span>  
  
 <span data-ttu-id="dc9f0-123">外接程序模型支持并建议在主机与外接程序之间构建可选边界，即隔离边界（也称为远程边界）。</span><span class="sxs-lookup"><span data-stu-id="dc9f0-123">The add-in model supports, and recommends, an optional boundary between the host and the add-in, which is called the isolation boundary (also known as a remoting boundary).</span></span> <span data-ttu-id="dc9f0-124">此边界可以是应用程序域边界或进程边界。</span><span class="sxs-lookup"><span data-stu-id="dc9f0-124">This boundary can be an application domain or process boundary.</span></span>  
  
 <span data-ttu-id="dc9f0-125">管道中间的合约段同时加载至主机的应用程序域和外接程序的应用程序域。</span><span class="sxs-lookup"><span data-stu-id="dc9f0-125">The contract segment in the middle of the pipeline is loaded into both the host's application domain and the add-in's application domain.</span></span> <span data-ttu-id="dc9f0-126">合约定义主机与外接程序用于互相交换类型的虚拟方式。</span><span class="sxs-lookup"><span data-stu-id="dc9f0-126">The contract defines the virtual methods that the host and the add-in use to exchange types with each other.</span></span>  
  
 <span data-ttu-id="dc9f0-127">若要通过隔离边界，则必须是合约或可序列化类型。</span><span class="sxs-lookup"><span data-stu-id="dc9f0-127">To pass through the isolation boundary, types must be either contracts or serializable types.</span></span> <span data-ttu-id="dc9f0-128">非合约或非可序列化类型必须由管道中的适配器段转换为合约。</span><span class="sxs-lookup"><span data-stu-id="dc9f0-128">Types that are not contracts or serializable types must be converted to contracts by the adapter segments in the pipeline.</span></span>  
  
 <span data-ttu-id="dc9f0-129">管道的视图段是抽象基类或接口，可为主机和外接程序提供它们共享的方式视图，如合约所定义。</span><span class="sxs-lookup"><span data-stu-id="dc9f0-129">The view segments of the pipeline are abstract base classes or interfaces that provide the host and the add-in with a view of the methods that they share, as defined by the contract.</span></span>  
  
 <span data-ttu-id="dc9f0-130">有关开发管道段的详细信息，请参阅 [Pipeline Development](../../../docs/framework/add-ins/pipeline-development.md)。</span><span class="sxs-lookup"><span data-stu-id="dc9f0-130">For more information about developing pipeline segments, see [Pipeline Development](../../../docs/framework/add-ins/pipeline-development.md).</span></span>  
  
 <span data-ttu-id="dc9f0-131">后面的部分介绍外接程序模型的功能。</span><span class="sxs-lookup"><span data-stu-id="dc9f0-131">The sections that follow describe the features of the add-in model.</span></span>  
  
### <a name="independent-versioning"></a><span data-ttu-id="dc9f0-132">独立版本控制</span><span class="sxs-lookup"><span data-stu-id="dc9f0-132">Independent Versioning</span></span>  
 <span data-ttu-id="dc9f0-133">外接程序模型允许主机和外接程序独立进行版本控制。</span><span class="sxs-lookup"><span data-stu-id="dc9f0-133">The add-in model allows hosts and add-ins to version independently.</span></span> <span data-ttu-id="dc9f0-134">正因如此，外接程序支持以下方案：</span><span class="sxs-lookup"><span data-stu-id="dc9f0-134">As a result, the add-in model enables the following scenarios:</span></span>  
  
-   <span data-ttu-id="dc9f0-135">创建适配器，使主机可以使用为旧主机版本生成的外接程序。</span><span class="sxs-lookup"><span data-stu-id="dc9f0-135">Creating an adapter that enables a host to use an add-in built for a previous version of the host.</span></span>  
  
-   <span data-ttu-id="dc9f0-136">创建适配器，使主机可以使用为新版本主机生成的外接程序。</span><span class="sxs-lookup"><span data-stu-id="dc9f0-136">Creating an adapter that enables a host to use an add-in built for a later version of the host.</span></span>  
  
-   <span data-ttu-id="dc9f0-137">创建适配器，使主机可以使用为其他主机生成的外接程序。</span><span class="sxs-lookup"><span data-stu-id="dc9f0-137">Creating an adapter that enables a host to use add-ins built for a different host.</span></span>  
  
### <a name="discovery-and-activation"></a><span data-ttu-id="dc9f0-138">发现和激活</span><span class="sxs-lookup"><span data-stu-id="dc9f0-138">Discovery and Activation</span></span>  
 <span data-ttu-id="dc9f0-139">可以使用表示从信息存储中找到的外接程序的集合中的令牌激活外接程序。</span><span class="sxs-lookup"><span data-stu-id="dc9f0-139">You can activate an add-in by using a token from a collection that represents the add-ins found from an information store.</span></span> <span data-ttu-id="dc9f0-140">通过搜索定义主机的外接程序视图的类型找到外接程序。</span><span class="sxs-lookup"><span data-stu-id="dc9f0-140">Add-ins are found by searching for the type that defines the host's view of the add-in.</span></span> <span data-ttu-id="dc9f0-141">还可以按定义外接程序的类型来查找特定的外接程序。</span><span class="sxs-lookup"><span data-stu-id="dc9f0-141">You can also find a specific add-in by the type that defines the add-in.</span></span> <span data-ttu-id="dc9f0-142">信息存储区包括两个缓存文件：管道存储区和外接程序存储区。</span><span class="sxs-lookup"><span data-stu-id="dc9f0-142">The information store consists of two cache files: the pipeline store and the add-in store.</span></span>  
  
 <span data-ttu-id="dc9f0-143">有关更新和重新生成的信息存储区的信息，请参阅[外接程序发现](https://msdn.microsoft.com/library/5d268dde-11df-4c4d-a022-f58d88bbc421)。</span><span class="sxs-lookup"><span data-stu-id="dc9f0-143">For information about updating and rebuilding the information store, see [Add-in Discovery](https://msdn.microsoft.com/library/5d268dde-11df-4c4d-a022-f58d88bbc421).</span></span> <span data-ttu-id="dc9f0-144">有关激活外接程序的信息，请参阅[外接程序激活](https://msdn.microsoft.com/library/bedcbcdf-5964-4215-b5f3-3299798b2b3f)并[如何： 激活外接程序具有不同的隔离和安全性](https://msdn.microsoft.com/library/7afe7ec8-5158-4350-9119-5df0ecab8aa5)。</span><span class="sxs-lookup"><span data-stu-id="dc9f0-144">For information about activating add-ins, see [Add-in Activation](https://msdn.microsoft.com/library/bedcbcdf-5964-4215-b5f3-3299798b2b3f) and [How to: Activate Add-ins with Different Isolation and Security](https://msdn.microsoft.com/library/7afe7ec8-5158-4350-9119-5df0ecab8aa5).</span></span>  
  
### <a name="isolation-levels-and-external-processes"></a><span data-ttu-id="dc9f0-145">隔离级别和外部进程</span><span class="sxs-lookup"><span data-stu-id="dc9f0-145">Isolation Levels and External Processes</span></span>  
 <span data-ttu-id="dc9f0-146">外接程序模型在外接程序与其主机之间或者两个外接程序之间支持几个隔离级别。这些隔离级别如下所示（从低到高顺序）：</span><span class="sxs-lookup"><span data-stu-id="dc9f0-146">The add-in model supports several levels of isolation between an add-in and its host or between add-ins. Starting from the least isolated, these levels are as follows:</span></span>  
  
-   <span data-ttu-id="dc9f0-147">外接程序在与主机相同的应用程序域中运行。</span><span class="sxs-lookup"><span data-stu-id="dc9f0-147">The add-in runs in the same application domain as the host.</span></span> <span data-ttu-id="dc9f0-148">不建议这样做，因为这不具备隔离和卸载功能，而使用不同的应用程序域时则可以获得这些功能。</span><span class="sxs-lookup"><span data-stu-id="dc9f0-148">This is not recommended because you lose the isolation and unloading capabilities that you get when you use different application domains.</span></span>  
  
-   <span data-ttu-id="dc9f0-149">多个外接程序加载到主机所使用应用程序域之外的同一应用程序域。</span><span class="sxs-lookup"><span data-stu-id="dc9f0-149">Multiple add-ins are loaded into the same application domain that is different from the application domain used by the host.</span></span>  
  
-   <span data-ttu-id="dc9f0-150">每个外接程序以独占方式加载到自己的应用程序域。</span><span class="sxs-lookup"><span data-stu-id="dc9f0-150">Each add-in is loaded exclusively into its own application domain.</span></span> <span data-ttu-id="dc9f0-151">这是最常见的隔离级别。</span><span class="sxs-lookup"><span data-stu-id="dc9f0-151">This is the most common level of isolation.</span></span>  
  
-   <span data-ttu-id="dc9f0-152">多个外接程序在外部进程中加载到同一应用程序域。</span><span class="sxs-lookup"><span data-stu-id="dc9f0-152">Multiple add-ins are loaded into the same application domain in an external process.</span></span>  
  
-   <span data-ttu-id="dc9f0-153">每个外接程序在外部进程中以独占方式加载到自己的应用程序域。</span><span class="sxs-lookup"><span data-stu-id="dc9f0-153">Each add-in is loaded exclusively into its own application domain in an external process.</span></span> <span data-ttu-id="dc9f0-154">这是最高级别的隔离方案。</span><span class="sxs-lookup"><span data-stu-id="dc9f0-154">This is the most isolated scenario.</span></span>  
  
 <span data-ttu-id="dc9f0-155">有关使用外部进程的详细信息，请参阅[如何： 激活外接程序具有不同的隔离和安全性](https://msdn.microsoft.com/library/7afe7ec8-5158-4350-9119-5df0ecab8aa5)。</span><span class="sxs-lookup"><span data-stu-id="dc9f0-155">For more information about using external processes, see [How to: Activate Add-ins with Different Isolation and Security](https://msdn.microsoft.com/library/7afe7ec8-5158-4350-9119-5df0ecab8aa5).</span></span>  
  
### <a name="lifetime-management"></a><span data-ttu-id="dc9f0-156">生存期管理</span><span class="sxs-lookup"><span data-stu-id="dc9f0-156">Lifetime Management</span></span>  
 <span data-ttu-id="dc9f0-157">由于外接程序模型跨应用程序域和进程边界，因此自身的垃圾回收不足以释放和回收对象。</span><span class="sxs-lookup"><span data-stu-id="dc9f0-157">Because the add-in model spans application domain and process boundaries, garbage collection by itself is not sufficient to release and reclaim objects.</span></span> <span data-ttu-id="dc9f0-158">外接程序模型提供一种生存期管理机制，该机制使用令牌和引用计数，并且通常不需要额外的编程。</span><span class="sxs-lookup"><span data-stu-id="dc9f0-158">The add-in model provides a lifetime management mechanism that uses tokens and reference counting, and usually does not require additional programming.</span></span> <span data-ttu-id="dc9f0-159">有关详细信息，请参阅[生存期管理](https://msdn.microsoft.com/library/57a9c87e-394c-4fef-89f2-aa4223a2aeb5)。</span><span class="sxs-lookup"><span data-stu-id="dc9f0-159">For more information, see [Lifetime Management](https://msdn.microsoft.com/library/57a9c87e-394c-4fef-89f2-aa4223a2aeb5).</span></span>  
  
 [<span data-ttu-id="dc9f0-160">返回页首</span><span class="sxs-lookup"><span data-stu-id="dc9f0-160">Back to top</span></span>](#top)  
  
<a name="distinguishing_between_addins_and_hosts"></a>   
## <a name="distinguishing-between-add-ins-and-hosts"></a><span data-ttu-id="dc9f0-161">区分外接程序和主机</span><span class="sxs-lookup"><span data-stu-id="dc9f0-161">Distinguishing Between Add-ins and Hosts</span></span>  
 <span data-ttu-id="dc9f0-162">外接程序与主机的区别仅仅是主机能够激活外接程序。</span><span class="sxs-lookup"><span data-stu-id="dc9f0-162">The difference between an add-in and a host is merely that the host is the one that activates the add-in.</span></span> <span data-ttu-id="dc9f0-163">主机可以是两个应用程序中较大的一个（如文字处理应用程序及其拼写检查器），也可以是两个应用程序中较小的一个（嵌入媒体播放中的即时消息客户端）。</span><span class="sxs-lookup"><span data-stu-id="dc9f0-163">The host can be the larger of the two, such as a word processing application and its spell checkers; or the host can be the smaller of the two, such as an instant messaging client that embeds a media player.</span></span> <span data-ttu-id="dc9f0-164">外接程序模型支持客户端和服务器方案中的外接程序。</span><span class="sxs-lookup"><span data-stu-id="dc9f0-164">The add-in model supports add-ins in both client and server scenarios.</span></span> <span data-ttu-id="dc9f0-165">服务器外接程序的示例包括为电子邮件服务器提供病毒扫描、垃圾邮件过滤以及 IP 保护的外接程序。</span><span class="sxs-lookup"><span data-stu-id="dc9f0-165">Examples of server add-ins include add-ins that provide mail servers with virus scanning, spam filters, and IP protection.</span></span> <span data-ttu-id="dc9f0-166">客户端外接程序示例包括引用的插件文字处理器、 图形程序和游戏和病毒扫描的本地电子邮件客户端的特殊功能。</span><span class="sxs-lookup"><span data-stu-id="dc9f0-166">Client add-in examples include reference add-ins for word processors, specialized features for graphics programs and games, and virus scanning for local email clients.</span></span>  
  
 [<span data-ttu-id="dc9f0-167">返回页首</span><span class="sxs-lookup"><span data-stu-id="dc9f0-167">Back to top</span></span>](#top)  
  
<a name="related_topics"></a>   
## <a name="related-topics"></a><span data-ttu-id="dc9f0-168">相关主题</span><span class="sxs-lookup"><span data-stu-id="dc9f0-168">Related Topics</span></span>  
  
|<span data-ttu-id="dc9f0-169">标题</span><span class="sxs-lookup"><span data-stu-id="dc9f0-169">Title</span></span>|<span data-ttu-id="dc9f0-170">描述</span><span class="sxs-lookup"><span data-stu-id="dc9f0-170">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="dc9f0-171">Pipeline Development</span><span class="sxs-lookup"><span data-stu-id="dc9f0-171">Pipeline Development</span></span>](../../../docs/framework/add-ins/pipeline-development.md)|<span data-ttu-id="dc9f0-172">描述从主机应用程序到外接程序之间的段的通信管道。</span><span class="sxs-lookup"><span data-stu-id="dc9f0-172">Describes the communication pipeline of segments from the host application to the add-in.</span></span> <span data-ttu-id="dc9f0-173">提供介绍如何构造管道以及如何将段部署到 Visual Studio 中的管道的演练主题中的代码示例。</span><span class="sxs-lookup"><span data-stu-id="dc9f0-173">Provides code examples in walkthrough topics that describe how to construct the pipeline and how to deploy segments to the pipeline in Visual Studio.</span></span>|  
|[<span data-ttu-id="dc9f0-174">应用程序域和程序集</span><span class="sxs-lookup"><span data-stu-id="dc9f0-174">Application Domains and Assemblies</span></span>](https://msdn.microsoft.com/library/433b04ae-4ba8-4849-9dbd-79194f240346)|<span data-ttu-id="dc9f0-175">描述（为安全性、可靠性和版本控制提供隔离边界的）应用程序域与程序集之间的关系。</span><span class="sxs-lookup"><span data-stu-id="dc9f0-175">Describes the relationship between application domains, which provide an isolation boundary for security, reliability, and versioning, and assemblies.</span></span>|  
  
 [<span data-ttu-id="dc9f0-176">返回页首</span><span class="sxs-lookup"><span data-stu-id="dc9f0-176">Back to top</span></span>](#top)  
  
<a name="reference"></a>   
## <a name="reference"></a><span data-ttu-id="dc9f0-177">参考</span><span class="sxs-lookup"><span data-stu-id="dc9f0-177">Reference</span></span>  
 <xref:System.AddIn?displayProperty=nameWithType>  
  
 <xref:System.AddIn.Contract?displayProperty=nameWithType>  
  
 <xref:System.AddIn.Hosting?displayProperty=nameWithType>  
  
 <xref:System.AddIn.Pipeline?displayProperty=nameWithType>  
  
 [<span data-ttu-id="dc9f0-178">返回页首</span><span class="sxs-lookup"><span data-stu-id="dc9f0-178">Back to top</span></span>](#top)