---
title: "使用 My 开发 (Visual Basic)"
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: My.MyWpfExtension.Windows
helpviewer_keywords:
- My object
- My namespace
- My feature
- Visual Basic, programming in
ms.assetid: f1d04509-5e46-4551-9f9f-94334a121fca
caps.latest.revision: "26"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 2cf51e1f6292a61c071fe6d92f5fcbce4be84ff4
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="development-with-my-visual-basic"></a><span data-ttu-id="1ec94-102">使用 My 开发 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1ec94-102">Development with My (Visual Basic)</span></span>
<span data-ttu-id="1ec94-103">Visual Basic 提供了支持快速应用程序开发的新功能，不仅功能强大，还有助于提高工作效率和易用性。</span><span class="sxs-lookup"><span data-stu-id="1ec94-103">Visual Basic provides new features for rapid application development that improve productivity and ease of use while delivering power.</span></span> <span data-ttu-id="1ec94-104">其中一项功能称为 `My`，可提供对与应用程序及其运行时环境相关的信息和默认对象实例的访问权限。</span><span class="sxs-lookup"><span data-stu-id="1ec94-104">One of these features, called `My`, provides access to information and default object instances that are related to the application and its run-time environment.</span></span> <span data-ttu-id="1ec94-105">此类信息按可通过 IntelliSense 搜索的格式进行编排，并根据用途进行了逻辑界定。</span><span class="sxs-lookup"><span data-stu-id="1ec94-105">This information is organized in a format that is discoverable through IntelliSense and logically delineated according to use.</span></span>  
  
 <span data-ttu-id="1ec94-106">`My` 的顶级成员作为对象公开。</span><span class="sxs-lookup"><span data-stu-id="1ec94-106">Top-level members of `My` are exposed as objects.</span></span> <span data-ttu-id="1ec94-107">每个对象的行为类似于包含 `Shared` 成员的命名空间或类，可公开一组相关成员。</span><span class="sxs-lookup"><span data-stu-id="1ec94-107">Each object behaves similarly to a namespace or a class with `Shared` members, and it exposes a set of related members.</span></span>  
  
 <span data-ttu-id="1ec94-108">下表展示了顶级 `My` 对象及其相互之间的关系。</span><span class="sxs-lookup"><span data-stu-id="1ec94-108">This table shows the top-level `My` objects and their relationship to each other.</span></span>  
  
 <span data-ttu-id="1ec94-109">![My 的对象模型](../../../visual-basic/developing-apps/development-with-my/media/myobjmodel.gif "MyObjModel")</span><span class="sxs-lookup"><span data-stu-id="1ec94-109">![Object Model for My](../../../visual-basic/developing-apps/development-with-my/media/myobjmodel.gif "MyObjModel")</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="1ec94-110">本节内容</span><span class="sxs-lookup"><span data-stu-id="1ec94-110">In This Section</span></span>  
 [<span data-ttu-id="1ec94-111">使用 My.Application、My.Computer 和 My.User 执行任务</span><span class="sxs-lookup"><span data-stu-id="1ec94-111">Performing Tasks with My.Application, My.Computer, and My.User</span></span>](../../../visual-basic/developing-apps/development-with-my/performing-tasks-with-my-application-my-computer-and-my-user.md)  
 <span data-ttu-id="1ec94-112">介绍了三个主要 `My` 对象（`My.Application`、`My.Computer` 和 `My.User`），这些对象提供对信息和功能的访问权限</span><span class="sxs-lookup"><span data-stu-id="1ec94-112">Describes the three central `My` objects, `My.Application`, `My.Computer`, and `My.User`, which provide access to information and functionality</span></span>  
  
 [<span data-ttu-id="1ec94-113">My.Forms 和 My.WebServices 提供的默认对象实例</span><span class="sxs-lookup"><span data-stu-id="1ec94-113">Default Object Instances Provided by My.Forms and My.WebServices</span></span>](../../../visual-basic/developing-apps/development-with-my/default-object-instances-provided-by-my-forms-and-my-webservices.md)  
 <span data-ttu-id="1ec94-114">介绍了 `My.Forms` 和 `My.WebServices` 对象，这些对象提供对应用程序使用的窗体、数据源和 XML Web Service 的访问权限。</span><span class="sxs-lookup"><span data-stu-id="1ec94-114">Describes the `My.Forms` and `My.WebServices` objects, which provide access to forms, data sources, and XML Web services used by your application.</span></span>  
  
 [<span data-ttu-id="1ec94-115">使用 My.Resources 和 My.Settings 快速开发应用程序</span><span class="sxs-lookup"><span data-stu-id="1ec94-115">Rapid Application Development with My.Resources and My.Settings</span></span>](../../../visual-basic/developing-apps/development-with-my/rapid-application-development-with-my-resources-and-my-settings.md)  
 <span data-ttu-id="1ec94-116">介绍了 `My.Resources` 和 `My.Settings` 对象，这些对象提供对应用程序资源和设置的访问权限。</span><span class="sxs-lookup"><span data-stu-id="1ec94-116">Describes the `My.Resources` and `My.Settings` objects, which provide access to an application's resources and settings.</span></span>  
  
 [<span data-ttu-id="1ec94-117">Visual Basic 应用程序模型概述</span><span class="sxs-lookup"><span data-stu-id="1ec94-117">Overview of the Visual Basic Application Model</span></span>](../../../visual-basic/developing-apps/development-with-my/overview-of-the-visual-basic-application-model.md)  
 <span data-ttu-id="1ec94-118">介绍了 [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] 应用程序启动/关闭模型。</span><span class="sxs-lookup"><span data-stu-id="1ec94-118">Describes the [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] Application Startup/Shutdown model.</span></span>  
  
 [<span data-ttu-id="1ec94-119">My 对项目类型的依赖方式</span><span class="sxs-lookup"><span data-stu-id="1ec94-119">How My Depends on Project Type</span></span>](../../../visual-basic/developing-apps/development-with-my/how-my-depends-on-project-type.md)  
 <span data-ttu-id="1ec94-120">详细介绍了不同项目类型中可用的 `My` 功能。</span><span class="sxs-lookup"><span data-stu-id="1ec94-120">Gives details on which `My` features are available in different project types.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1ec94-121">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1ec94-121">See Also</span></span>  
 <xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase>  
 <xref:Microsoft.VisualBasic.Devices.Computer>  
 <xref:Microsoft.VisualBasic.ApplicationServices.User>  
 [<span data-ttu-id="1ec94-122">My.Forms 对象</span><span class="sxs-lookup"><span data-stu-id="1ec94-122">My.Forms Object</span></span>](../../../visual-basic/language-reference/objects/my-forms-object.md)  
 [<span data-ttu-id="1ec94-123">My.WebServices 对象</span><span class="sxs-lookup"><span data-stu-id="1ec94-123">My.WebServices Object</span></span>](../../../visual-basic/language-reference/objects/my-webservices-object.md)  
 [<span data-ttu-id="1ec94-124">My 对项目类型的依赖方式</span><span class="sxs-lookup"><span data-stu-id="1ec94-124">How My Depends on Project Type</span></span>](../../../visual-basic/developing-apps/development-with-my/how-my-depends-on-project-type.md)
