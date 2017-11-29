---
title: "开发 Windows 服务应用程序"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- ServiceInstaller class, Windows Service applications
- Service class, Windows Service applications
- Windows Service applications
- Windows NT services
- ServiceProcessInstaller class, Windows Service applications
- services
- .NET applications, Windows applications
ms.assetid: ba72d648-9553-4849-b829-069ad5ea014b
caps.latest.revision: "18"
author: ghogen
ms.author: ghogen
manager: douge
ms.openlocfilehash: 2912568e967c8c6096842b1b4f24eac88318dffb
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="developing-windows-service-applications"></a><span data-ttu-id="f2501-102">开发 Windows 服务应用程序</span><span class="sxs-lookup"><span data-stu-id="f2501-102">Developing Windows Service Applications</span></span>
<span data-ttu-id="f2501-103">使用 Microsoft[!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)]或 Microsoft [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] SDK，你可以轻松创建服务通过创建作为服务安装的应用程序。</span><span class="sxs-lookup"><span data-stu-id="f2501-103">Using Microsoft [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] or the Microsoft [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] SDK, you can easily create services by creating an application that is installed as a service.</span></span> <span data-ttu-id="f2501-104">此类型的应用程序称为 Windows 服务。</span><span class="sxs-lookup"><span data-stu-id="f2501-104">This type of application is called a Windows service.</span></span> <span data-ttu-id="f2501-105">使用框架功能，可以创建服务、 安装它们，并启动、 停止和以其他方式控制其行为。</span><span class="sxs-lookup"><span data-stu-id="f2501-105">With framework features, you can create services, install them, and start, stop, and otherwise control their behavior.</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="f2501-106">Visual Studio 2010 中未包括 c + + 的 Windows 服务模板。</span><span class="sxs-lookup"><span data-stu-id="f2501-106">The Windows service template for C++ was not included in Visual Studio 2010.</span></span> <span data-ttu-id="f2501-107">若要创建 Windows 服务，你可以在 Visual C# 或 Visual Basic，无法与现有的 c + + 代码，如果需要互操作，在托管代码中创建服务，或可以通过在本机 c + + 创建 Windows 服务[ATL 项目向导](/cpp/atl/reference/atl-project-wizard).</span><span class="sxs-lookup"><span data-stu-id="f2501-107">To create a Windows service, you can either create a service in managed code in Visual C# or Visual Basic, which could interoperate with existing C++ code if required, or you can create a Windows service in native C++ by using the [ATL Project Wizard](/cpp/atl/reference/atl-project-wizard).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="f2501-108">本节内容</span><span class="sxs-lookup"><span data-stu-id="f2501-108">In This Section</span></span>  
 [<span data-ttu-id="f2501-109">Windows 服务应用程序简介</span><span class="sxs-lookup"><span data-stu-id="f2501-109">Introduction to Windows Service Applications</span></span>](../../../docs/framework/windows-services/introduction-to-windows-service-applications.md)  
 <span data-ttu-id="f2501-110">概述介绍 Windows 服务应用程序，一种服务，以及服务应用程序与其他常见的项目类型的区别的生存期。</span><span class="sxs-lookup"><span data-stu-id="f2501-110">Provides an overview of Windows service applications, the lifetime of a service, and how service applications differ from other common project types.</span></span>  
  
 [<span data-ttu-id="f2501-111">演练： 在组件设计器中创建 Windows 服务应用程序</span><span class="sxs-lookup"><span data-stu-id="f2501-111">Walkthrough: Creating a Windows Service Application in the Component Designer</span></span>](../../../docs/framework/windows-services/walkthrough-creating-a-windows-service-application-in-the-component-designer.md)  
 <span data-ttu-id="f2501-112">提供创建中的服务的示例[!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]和 Visual C#。</span><span class="sxs-lookup"><span data-stu-id="f2501-112">Provides an example of creating a service in [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)] and Visual C#.</span></span>  
  
 [<span data-ttu-id="f2501-113">服务应用程序编程体系结构</span><span class="sxs-lookup"><span data-stu-id="f2501-113">Service Application Programming Architecture</span></span>](../../../docs/framework/windows-services/service-application-programming-architecture.md)  
 <span data-ttu-id="f2501-114">说明在服务编程中使用的语言元素。</span><span class="sxs-lookup"><span data-stu-id="f2501-114">Explains the language elements used in service programming.</span></span>  
  
 [<span data-ttu-id="f2501-115">如何： 创建 Windows 服务</span><span class="sxs-lookup"><span data-stu-id="f2501-115">How to: Create Windows Services</span></span>](../../../docs/framework/windows-services/how-to-create-windows-services.md)  
 <span data-ttu-id="f2501-116">介绍创建和配置使用 Windows 服务项目模板的 Windows 服务的过程。</span><span class="sxs-lookup"><span data-stu-id="f2501-116">Describes the process of creating and configuring Windows services using the Windows service project template.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="f2501-117">相关章节</span><span class="sxs-lookup"><span data-stu-id="f2501-117">Related Sections</span></span>  
 <xref:System.ServiceProcess.ServiceBase>  
 <span data-ttu-id="f2501-118">描述的主要功能<xref:System.ServiceProcess.ServiceBase>类，该类用于创建服务。</span><span class="sxs-lookup"><span data-stu-id="f2501-118">Describes the major features of the <xref:System.ServiceProcess.ServiceBase> class, which is used to create services.</span></span>  
  
 <xref:System.ServiceProcess.ServiceProcessInstaller>  
 <span data-ttu-id="f2501-119">介绍的功能<xref:System.ServiceProcess.ServiceProcessInstaller>类，该类用于连同<xref:System.ServiceProcess.ServiceInstaller>类用于安装和卸载你的服务。</span><span class="sxs-lookup"><span data-stu-id="f2501-119">Describes the features of the <xref:System.ServiceProcess.ServiceProcessInstaller> class, which is used along with the <xref:System.ServiceProcess.ServiceInstaller> class to install and uninstall your services.</span></span>  
  
 <xref:System.ServiceProcess.ServiceInstaller>  
 <span data-ttu-id="f2501-120">介绍的功能<xref:System.ServiceProcess.ServiceInstaller>类，该类用于连同<xref:System.ServiceProcess.ServiceProcessInstaller>类用于安装和卸载你的服务。</span><span class="sxs-lookup"><span data-stu-id="f2501-120">Describes the features of the <xref:System.ServiceProcess.ServiceInstaller> class, which is used along with the <xref:System.ServiceProcess.ServiceProcessInstaller> class to install and uninstall your service.</span></span>  
  
 [<span data-ttu-id="f2501-121">NIB 从模板创建项目</span><span class="sxs-lookup"><span data-stu-id="f2501-121">NIB Creating Projects from Templates</span></span>](http://msdn.microsoft.com/en-us/7c36d86a-6b79-4480-8228-0f925f1204b2)  
 <span data-ttu-id="f2501-122">描述项目中这一章以及如何选择它们之间使用的类型。</span><span class="sxs-lookup"><span data-stu-id="f2501-122">Describes the projects types used in this chapter and how to choose between them.</span></span>
