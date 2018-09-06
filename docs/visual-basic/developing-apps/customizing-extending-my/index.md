---
title: 利用 Visual Basic 自定义项目并扩展 My 对象
ms.date: 07/20/2015
helpviewer_keywords:
- My namespace [Visual Basic], customizing
- My namespace
- My namespace [Visual Basic], extending
ms.assetid: 06ca80b9-1192-4eb5-8537-8ef5edfb9be0
ms.openlocfilehash: 4dfe14f7680ad0c3a302334c07bb17e3e92011b0
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/05/2018
ms.locfileid: "43786976"
---
# <a name="customizing-projects-and-extending-my-with-visual-basic"></a><span data-ttu-id="91b72-102">利用 Visual Basic 自定义项目并扩展 My 对象</span><span class="sxs-lookup"><span data-stu-id="91b72-102">Customizing Projects and Extending My with Visual Basic</span></span>
<span data-ttu-id="91b72-103">你可以自定义项目模板，以提供其他`My`对象。</span><span class="sxs-lookup"><span data-stu-id="91b72-103">You can customize project templates to provide additional `My` objects.</span></span> <span data-ttu-id="91b72-104">这样方便其他开发人员查找并使用您的对象。</span><span class="sxs-lookup"><span data-stu-id="91b72-104">This makes it easy for other developers to find and use your objects.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="91b72-105">本节内容</span><span class="sxs-lookup"><span data-stu-id="91b72-105">In This Section</span></span>  
 [<span data-ttu-id="91b72-106">扩展 Visual Basic 中的 My 命名空间</span><span class="sxs-lookup"><span data-stu-id="91b72-106">Extending the My Namespace in Visual Basic</span></span>](../../../visual-basic/developing-apps/customizing-extending-my/extending-the-my-namespace.md)  
 <span data-ttu-id="91b72-107">描述如何添加自定义成员和值添加到`My`在 Visual Basic 中的命名空间。</span><span class="sxs-lookup"><span data-stu-id="91b72-107">Describes how to add custom members and values to the `My` namespace in Visual Basic.</span></span>  
  
 [<span data-ttu-id="91b72-108">打包和部署自定义 My 扩展</span><span class="sxs-lookup"><span data-stu-id="91b72-108">Packaging and Deploying Custom My Extensions</span></span>](../../../visual-basic/developing-apps/customizing-extending-my/packaging-and-deploying-custom-my-extensions.md)  
 <span data-ttu-id="91b72-109">描述如何发布自定义`My`通过使用 Visual Studio 模板的命名空间扩展。</span><span class="sxs-lookup"><span data-stu-id="91b72-109">Describes how to publish custom `My` namespace extensions by using Visual Studio templates.</span></span>  
  
 [<span data-ttu-id="91b72-110">扩展 Visual Basic 应用程序模型</span><span class="sxs-lookup"><span data-stu-id="91b72-110">Extending the Visual Basic Application Model</span></span>](../../../visual-basic/developing-apps/customizing-extending-my/extending-the-visual-basic-application-model.md)  
 <span data-ttu-id="91b72-111">介绍如何通过重写的成员指定你自己的扩展到应用程序模型<xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase>类。</span><span class="sxs-lookup"><span data-stu-id="91b72-111">Describes how to specify your own extensions to the application model by overriding members of the <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase> class.</span></span>  
  
 [<span data-ttu-id="91b72-112">自定义 My 中可用的对象</span><span class="sxs-lookup"><span data-stu-id="91b72-112">Customizing Which Objects are Available in My</span></span>](../../../visual-basic/developing-apps/customizing-extending-my/customizing-which-objects-are-available-in-my.md)  
 <span data-ttu-id="91b72-113">介绍如何控制哪些`My`对象启用通过设置项目的 _MYTYPE 条件编译常量。</span><span class="sxs-lookup"><span data-stu-id="91b72-113">Describes how to control which `My` objects are enabled by setting your project's _MYTYPE conditional-compilation constant.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="91b72-114">相关章节</span><span class="sxs-lookup"><span data-stu-id="91b72-114">Related Sections</span></span>  
 [<span data-ttu-id="91b72-115">使用 My 开发</span><span class="sxs-lookup"><span data-stu-id="91b72-115">Development with My</span></span>](../../../visual-basic/developing-apps/development-with-my/index.md)  
 <span data-ttu-id="91b72-116">描述该`My`对象是在默认情况下的不同项目类型中可用。</span><span class="sxs-lookup"><span data-stu-id="91b72-116">Describes which `My` objects are available in different project types by default.</span></span>  
  
 [<span data-ttu-id="91b72-117">Visual Basic 应用程序模型概述</span><span class="sxs-lookup"><span data-stu-id="91b72-117">Overview of the Visual Basic Application Model</span></span>](../../../visual-basic/developing-apps/development-with-my/overview-of-the-visual-basic-application-model.md)  
 <span data-ttu-id="91b72-118">描述用于控制 Windows 窗体应用程序的行为的 Visual Basic 的模型。</span><span class="sxs-lookup"><span data-stu-id="91b72-118">Describes Visual Basic's model for controlling the behavior of Windows Forms applications.</span></span>  
  
 [<span data-ttu-id="91b72-119">My 对项目类型的依赖方式</span><span class="sxs-lookup"><span data-stu-id="91b72-119">How My Depends on Project Type</span></span>](../../../visual-basic/developing-apps/development-with-my/how-my-depends-on-project-type.md)  
 <span data-ttu-id="91b72-120">描述该`My`对象是在默认情况下的不同项目类型中可用。</span><span class="sxs-lookup"><span data-stu-id="91b72-120">Describes which `My` objects are available in different project types by default.</span></span>  
  
 [<span data-ttu-id="91b72-121">条件编译</span><span class="sxs-lookup"><span data-stu-id="91b72-121">Conditional Compilation</span></span>](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)  
 <span data-ttu-id="91b72-122">讨论编译器如何使用条件编译来选择特定部分的代码可以编译并排除其他部分。</span><span class="sxs-lookup"><span data-stu-id="91b72-122">Discusses how the compiler uses conditional-compilation to select particular sections of code to compile and exclude other sections.</span></span>  
  
 <xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase>  
 <span data-ttu-id="91b72-123">介绍`My`提供属性、 方法和事件的对象与当前应用程序相关。</span><span class="sxs-lookup"><span data-stu-id="91b72-123">Describes the `My` object that provides properties, methods, and events related to the current application.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="91b72-124">请参阅</span><span class="sxs-lookup"><span data-stu-id="91b72-124">See Also</span></span>  
 [<span data-ttu-id="91b72-125">使用 Visual Basic 开发应用程序</span><span class="sxs-lookup"><span data-stu-id="91b72-125">Developing Applications with Visual Basic</span></span>](../../../visual-basic/developing-apps/index.md)
