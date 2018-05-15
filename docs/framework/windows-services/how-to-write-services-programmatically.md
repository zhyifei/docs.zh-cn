---
title: 如何：以编程方式编写服务
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- services, creating
- Windows Service applications, creating
ms.assetid: 3abbb2ec-78d2-41e6-b9f9-6662d4e2cdc7
author: ghogen
manager: douge
ms.openlocfilehash: 99fd44723bba21127e2a5e0ba3e9bfc4b90b52d7
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-write-services-programmatically"></a><span data-ttu-id="65a1b-102">如何：以编程方式编写服务</span><span class="sxs-lookup"><span data-stu-id="65a1b-102">How to: Write Services Programmatically</span></span>
<span data-ttu-id="65a1b-103">如果你选择不使用 Windows 服务项目模板，你可以通过设置继承和其他基础结构元素自己编写你自己的服务。</span><span class="sxs-lookup"><span data-stu-id="65a1b-103">If you choose not to use the Windows Service project template, you can write your own services by setting up the inheritance and other infrastructure elements yourself.</span></span> <span data-ttu-id="65a1b-104">当以编程方式创建服务时，你必须执行该模板将为您处理的几个步骤：</span><span class="sxs-lookup"><span data-stu-id="65a1b-104">When you create a service programmatically, you must perform several steps that the template would otherwise handle for you:</span></span>  
  
-   <span data-ttu-id="65a1b-105">必须设置服务类继承自<xref:System.ServiceProcess.ServiceBase>类。</span><span class="sxs-lookup"><span data-stu-id="65a1b-105">You must set up your service class to inherit from the <xref:System.ServiceProcess.ServiceBase> class.</span></span>  
  
-   <span data-ttu-id="65a1b-106">你必须创建`Main`用于定义要运行的服务的服务项目和调用方法<xref:System.ServiceProcess.ServiceBase.Run%2A>对它们的方法。</span><span class="sxs-lookup"><span data-stu-id="65a1b-106">You must create a `Main` method for your service project that defines the services to run and calls the <xref:System.ServiceProcess.ServiceBase.Run%2A> method on them.</span></span>  
  
-   <span data-ttu-id="65a1b-107">必须重写<xref:System.ServiceProcess.ServiceBase.OnStart%2A>和<xref:System.ServiceProcess.ServiceBase.OnStop%2A>过程和任何代码填写你想要运行。</span><span class="sxs-lookup"><span data-stu-id="65a1b-107">You must override the <xref:System.ServiceProcess.ServiceBase.OnStart%2A> and <xref:System.ServiceProcess.ServiceBase.OnStop%2A> procedures and fill in any code you want them to run.</span></span>  
  
### <a name="to-write-a-service-programmatically"></a><span data-ttu-id="65a1b-108">若要以编程方式编写服务</span><span class="sxs-lookup"><span data-stu-id="65a1b-108">To write a service programmatically</span></span>  
  
1.  <span data-ttu-id="65a1b-109">按照这些步骤创建必要的命名空间的引用并创建一个空项目：</span><span class="sxs-lookup"><span data-stu-id="65a1b-109">Create an empty project and create a reference to the necessary namespaces by following these steps:</span></span>  
  
    1.  <span data-ttu-id="65a1b-110">在**解决方案资源管理器**，右键单击**引用**节点，然后单击**添加引用**。</span><span class="sxs-lookup"><span data-stu-id="65a1b-110">In **Solution Explorer**, right-click the **References** node and click **Add Reference**.</span></span>  
  
    2.  <span data-ttu-id="65a1b-111">上 **.NET Framework**选项卡上，向下滚动到**System.dll**单击**选择**。</span><span class="sxs-lookup"><span data-stu-id="65a1b-111">On the **.NET Framework** tab, scroll to **System.dll** and click **Select**.</span></span>  
  
    3.  <span data-ttu-id="65a1b-112">滚动到**System.ServiceProcess.dll**单击**选择**。</span><span class="sxs-lookup"><span data-stu-id="65a1b-112">Scroll to **System.ServiceProcess.dll** and click **Select**.</span></span>  
  
    4.  <span data-ttu-id="65a1b-113">单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="65a1b-113">Click **OK**.</span></span>  
  
2.  <span data-ttu-id="65a1b-114">添加类并将其配置为从继承<xref:System.ServiceProcess.ServiceBase>:</span><span class="sxs-lookup"><span data-stu-id="65a1b-114">Add a class and configure it to inherit from <xref:System.ServiceProcess.ServiceBase>:</span></span>  
  
     [!code-csharp[VbRadconService#7](../../../samples/snippets/csharp/VS_Snippets_VBCSharp/VbRadconService/CS/MyNewService.cs#7)]
     [!code-vb[VbRadconService#7](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#7)]  
  
3.  <span data-ttu-id="65a1b-115">添加以下代码来配置你的服务类：</span><span class="sxs-lookup"><span data-stu-id="65a1b-115">Add the following code to configure your service class:</span></span>  
  
     [!code-csharp[VbRadconService#8](../../../samples/snippets/csharp/VS_Snippets_VBCSharp/VbRadconService/CS/MyNewService.cs#8)]
     [!code-vb[VbRadconService#8](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#8)]  
  
4.  <span data-ttu-id="65a1b-116">创建`Main`方法为您的类，并用它来定义你的类将包含; 的服务`userService1`是类的名称：</span><span class="sxs-lookup"><span data-stu-id="65a1b-116">Create a `Main` method for your class, and use it to define the service your class will contain; `userService1` is the name of the class:</span></span>  
  
     [!code-csharp[VbRadconService#9](../../../samples/snippets/csharp/VS_Snippets_VBCSharp/VbRadconService/CS/MyNewService.cs#9)]
     [!code-vb[VbRadconService#9](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#9)]  
  
5.  <span data-ttu-id="65a1b-117">重写<xref:System.ServiceProcess.ServiceBase.OnStart%2A>方法，并定义你希望你的服务启动时执行任何的处理。</span><span class="sxs-lookup"><span data-stu-id="65a1b-117">Override the <xref:System.ServiceProcess.ServiceBase.OnStart%2A> method, and define any processing you want to occur when your service is started.</span></span>  
  
     [!code-csharp[VbRadconService#10](../../../samples/snippets/csharp/VS_Snippets_VBCSharp/VbRadconService/CS/MyNewService.cs#10)]
     [!code-vb[VbRadconService#10](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#10)]  
  
6.  <span data-ttu-id="65a1b-118">替代你想要定义自定义，处理的任何其他方法，并编写代码来确定服务中每种情况下应采取的操作。</span><span class="sxs-lookup"><span data-stu-id="65a1b-118">Override any other methods you want to define custom processing for, and write code to determine the actions the service should take in each case.</span></span>  
  
7.  <span data-ttu-id="65a1b-119">添加服务应用程序所必需的安装程序。</span><span class="sxs-lookup"><span data-stu-id="65a1b-119">Add the necessary installers for your service application.</span></span> <span data-ttu-id="65a1b-120">有关详细信息，请参阅[如何： 添加到你的服务应用程序的安装程序](../../../docs/framework/windows-services/how-to-add-installers-to-your-service-application.md)。</span><span class="sxs-lookup"><span data-stu-id="65a1b-120">For more information, see [How to: Add Installers to Your Service Application](../../../docs/framework/windows-services/how-to-add-installers-to-your-service-application.md).</span></span>  
  
8.  <span data-ttu-id="65a1b-121">通过选择生成你的项目**生成解决方案**从**生成**菜单。</span><span class="sxs-lookup"><span data-stu-id="65a1b-121">Build your project by selecting **Build Solution** from the **Build** menu.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="65a1b-122">不要通过按 F5 来运行你的项目 — 你无法通过这种方式运行服务项目。</span><span class="sxs-lookup"><span data-stu-id="65a1b-122">Do not press F5 to run your project — you cannot run a service project in this way.</span></span>  
  
9. <span data-ttu-id="65a1b-123">创建安装项目和安装你的服务的自定义操作。</span><span class="sxs-lookup"><span data-stu-id="65a1b-123">Create a setup project and the custom actions to install your service.</span></span> <span data-ttu-id="65a1b-124">有关示例，请参阅[演练： 在组件设计器中创建 Windows 服务应用程序](../../../docs/framework/windows-services/walkthrough-creating-a-windows-service-application-in-the-component-designer.md)。</span><span class="sxs-lookup"><span data-stu-id="65a1b-124">For an example, see [Walkthrough: Creating a Windows Service Application in the Component Designer](../../../docs/framework/windows-services/walkthrough-creating-a-windows-service-application-in-the-component-designer.md).</span></span>  
  
10. <span data-ttu-id="65a1b-125">安装服务。</span><span class="sxs-lookup"><span data-stu-id="65a1b-125">Install the service.</span></span> <span data-ttu-id="65a1b-126">有关更多信息，请参见 [How to: Install and Uninstall Services](../../../docs/framework/windows-services/how-to-install-and-uninstall-services.md)。</span><span class="sxs-lookup"><span data-stu-id="65a1b-126">For more information, see [How to: Install and Uninstall Services](../../../docs/framework/windows-services/how-to-install-and-uninstall-services.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="65a1b-127">请参阅</span><span class="sxs-lookup"><span data-stu-id="65a1b-127">See Also</span></span>  
 [<span data-ttu-id="65a1b-128">Windows 服务应用程序介绍</span><span class="sxs-lookup"><span data-stu-id="65a1b-128">Introduction to Windows Service Applications</span></span>](../../../docs/framework/windows-services/introduction-to-windows-service-applications.md)  
 [<span data-ttu-id="65a1b-129">如何：创建 Windows 服务</span><span class="sxs-lookup"><span data-stu-id="65a1b-129">How to: Create Windows Services</span></span>](../../../docs/framework/windows-services/how-to-create-windows-services.md)  
 [<span data-ttu-id="65a1b-130">如何：将安装程序添加到服务应用程序</span><span class="sxs-lookup"><span data-stu-id="65a1b-130">How to: Add Installers to Your Service Application</span></span>](../../../docs/framework/windows-services/how-to-add-installers-to-your-service-application.md)  
 [<span data-ttu-id="65a1b-131">如何：记录关于服务的信息</span><span class="sxs-lookup"><span data-stu-id="65a1b-131">How to: Log Information About Services</span></span>](../../../docs/framework/windows-services/how-to-log-information-about-services.md)  
 [<span data-ttu-id="65a1b-132">演练：在组件设计器中创建 Windows 服务应用程序</span><span class="sxs-lookup"><span data-stu-id="65a1b-132">Walkthrough: Creating a Windows Service Application in the Component Designer</span></span>](../../../docs/framework/windows-services/walkthrough-creating-a-windows-service-application-in-the-component-designer.md)
