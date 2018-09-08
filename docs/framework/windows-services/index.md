---
title: 开发 Windows 服务应用程序
ms.date: 03/30/2017
helpviewer_keywords:
- ServiceInstaller class, Windows Service applications
- Service class, Windows Service applications
- Windows Service applications
- Windows NT services
- ServiceProcessInstaller class, Windows Service applications
- services
- .NET applications, Windows applications
ms.assetid: ba72d648-9553-4849-b829-069ad5ea014b
author: ghogen
manager: douge
ms.openlocfilehash: 2c7fb148b96d5ff9804bcb0bb7c842c475c0f117
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/08/2018
ms.locfileid: "44207091"
---
# <a name="developing-windows-service-applications"></a><span data-ttu-id="d5a0f-102">开发 Windows 服务应用程序</span><span class="sxs-lookup"><span data-stu-id="d5a0f-102">Developing Windows Service Applications</span></span>
<span data-ttu-id="d5a0f-103">使用 Microsoft Visual Studio 或 Microsoft [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] SDK，可以通过创建作为服务安装的应用程序来轻松创建服务。</span><span class="sxs-lookup"><span data-stu-id="d5a0f-103">Using Microsoft Visual Studio or the Microsoft [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] SDK, you can easily create services by creating an application that is installed as a service.</span></span> <span data-ttu-id="d5a0f-104">这种类型的应用程序称为 Windows 服务。</span><span class="sxs-lookup"><span data-stu-id="d5a0f-104">This type of application is called a Windows service.</span></span> <span data-ttu-id="d5a0f-105">借助框架功能，可以创建、安装服务，启动、停止服务并及控制服务的行为。</span><span class="sxs-lookup"><span data-stu-id="d5a0f-105">With framework features, you can create services, install them, and start, stop, and otherwise control their behavior.</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="d5a0f-106">C++ 的 Windows 服务模板未包含在 Visual Studio 2010 中。</span><span class="sxs-lookup"><span data-stu-id="d5a0f-106">The Windows service template for C++ was not included in Visual Studio 2010.</span></span> <span data-ttu-id="d5a0f-107">要创建 Windows 服务，可以在 Visual C# 或 Visual Basic 的托管代码中创建服务（如有必要，该服务可与现有 C++ 代码进行互操作），也可以使用 [ATL 项目向导](/cpp/atl/reference/atl-project-wizard)在本机 C++ 中创建 Windows 服务。</span><span class="sxs-lookup"><span data-stu-id="d5a0f-107">To create a Windows service, you can either create a service in managed code in Visual C# or Visual Basic, which could interoperate with existing C++ code if required, or you can create a Windows service in native C++ by using the [ATL Project Wizard](/cpp/atl/reference/atl-project-wizard).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="d5a0f-108">本节内容</span><span class="sxs-lookup"><span data-stu-id="d5a0f-108">In This Section</span></span>  
 [<span data-ttu-id="d5a0f-109">Windows 服务应用程序介绍</span><span class="sxs-lookup"><span data-stu-id="d5a0f-109">Introduction to Windows Service Applications</span></span>](../../../docs/framework/windows-services/introduction-to-windows-service-applications.md)  
 <span data-ttu-id="d5a0f-110">提供 Windows 服务应用程序、服务生存期以及服务应用程序与其他常见项目类型的区别的概述。</span><span class="sxs-lookup"><span data-stu-id="d5a0f-110">Provides an overview of Windows service applications, the lifetime of a service, and how service applications differ from other common project types.</span></span>  
  
 [<span data-ttu-id="d5a0f-111">演练：在组件设计器中创建 Windows 服务应用程序</span><span class="sxs-lookup"><span data-stu-id="d5a0f-111">Walkthrough: Creating a Windows Service Application in the Component Designer</span></span>](../../../docs/framework/windows-services/walkthrough-creating-a-windows-service-application-in-the-component-designer.md)  
 <span data-ttu-id="d5a0f-112">提供在 Visual Basic 和 Visual C# 中创建服务的示例。</span><span class="sxs-lookup"><span data-stu-id="d5a0f-112">Provides an example of creating a service in Visual Basic and Visual C#.</span></span>  
  
 [<span data-ttu-id="d5a0f-113">服务应用程序编程体系结构</span><span class="sxs-lookup"><span data-stu-id="d5a0f-113">Service Application Programming Architecture</span></span>](../../../docs/framework/windows-services/service-application-programming-architecture.md)  
 <span data-ttu-id="d5a0f-114">介绍服务编程中使用的语言元素。</span><span class="sxs-lookup"><span data-stu-id="d5a0f-114">Explains the language elements used in service programming.</span></span>  
  
 [<span data-ttu-id="d5a0f-115">如何：创建 Windows 服务</span><span class="sxs-lookup"><span data-stu-id="d5a0f-115">How to: Create Windows Services</span></span>](../../../docs/framework/windows-services/how-to-create-windows-services.md)  
 <span data-ttu-id="d5a0f-116">介绍使用 Windows 服务项目模板创建和配置 Windows 服务的过程。</span><span class="sxs-lookup"><span data-stu-id="d5a0f-116">Describes the process of creating and configuring Windows services using the Windows service project template.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="d5a0f-117">相关章节</span><span class="sxs-lookup"><span data-stu-id="d5a0f-117">Related Sections</span></span>  
 <xref:System.ServiceProcess.ServiceBase>  
 <span data-ttu-id="d5a0f-118">介绍用于创建服务的 <xref:System.ServiceProcess.ServiceBase> 类的主要功能。</span><span class="sxs-lookup"><span data-stu-id="d5a0f-118">Describes the major features of the <xref:System.ServiceProcess.ServiceBase> class, which is used to create services.</span></span>  
  
 <xref:System.ServiceProcess.ServiceProcessInstaller>  
 <span data-ttu-id="d5a0f-119">介绍 <xref:System.ServiceProcess.ServiceProcessInstaller> 类的功能，该类与 <xref:System.ServiceProcess.ServiceInstaller> 类一起用于安装和卸载服务。</span><span class="sxs-lookup"><span data-stu-id="d5a0f-119">Describes the features of the <xref:System.ServiceProcess.ServiceProcessInstaller> class, which is used along with the <xref:System.ServiceProcess.ServiceInstaller> class to install and uninstall your services.</span></span>  
  
 <xref:System.ServiceProcess.ServiceInstaller>  
 <span data-ttu-id="d5a0f-120">介绍 <xref:System.ServiceProcess.ServiceInstaller> 类的功能，该类与 <xref:System.ServiceProcess.ServiceProcessInstaller> 类一起用于安装和卸载服务。</span><span class="sxs-lookup"><span data-stu-id="d5a0f-120">Describes the features of the <xref:System.ServiceProcess.ServiceInstaller> class, which is used along with the <xref:System.ServiceProcess.ServiceProcessInstaller> class to install and uninstall your service.</span></span>  
  
 [<span data-ttu-id="d5a0f-121">NIB 从模板创建项目</span><span class="sxs-lookup"><span data-stu-id="d5a0f-121">NIB Creating Projects from Templates</span></span>](https://msdn.microsoft.com/library/7c36d86a-6b79-4480-8228-0f925f1204b2)  
 <span data-ttu-id="d5a0f-122">介绍本章中使用的项目类型以及如何从中进行选择。</span><span class="sxs-lookup"><span data-stu-id="d5a0f-122">Describes the projects types used in this chapter and how to choose between them.</span></span>
