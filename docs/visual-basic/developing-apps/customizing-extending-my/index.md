---
title: 利用 Visual Basic 自定义项目并扩展 My 对象
ms.date: 07/20/2015
helpviewer_keywords:
- My namespace [Visual Basic], customizing
- My namespace
- My namespace [Visual Basic], extending
ms.assetid: 06ca80b9-1192-4eb5-8537-8ef5edfb9be0
ms.openlocfilehash: 97933a9d014a54d5b6e333090cddccace99fcc3c
ms.sourcegitcommit: 9b2ef64c4fc10a4a10f28a223d60d17d7d249ee8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/26/2019
ms.locfileid: "72960945"
---
# <a name="customizing-projects-and-extending-my-with-visual-basic"></a><span data-ttu-id="5eb6f-102">利用 Visual Basic 自定义项目并扩展 My 对象</span><span class="sxs-lookup"><span data-stu-id="5eb6f-102">Customizing Projects and Extending My with Visual Basic</span></span>

<span data-ttu-id="5eb6f-103">你可以自定义项目模板以提供额外的 `My` 对象。</span><span class="sxs-lookup"><span data-stu-id="5eb6f-103">You can customize project templates to provide additional `My` objects.</span></span> <span data-ttu-id="5eb6f-104">这样，其他开发人员便可以轻松查找和使用您的对象。</span><span class="sxs-lookup"><span data-stu-id="5eb6f-104">This makes it easy for other developers to find and use your objects.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="5eb6f-105">本节内容</span><span class="sxs-lookup"><span data-stu-id="5eb6f-105">In this section</span></span>

- [<span data-ttu-id="5eb6f-106">扩展 Visual Basic 中的 My 命名空间</span><span class="sxs-lookup"><span data-stu-id="5eb6f-106">Extending the My Namespace in Visual Basic</span></span>](extending-the-my-namespace.md)  
 <span data-ttu-id="5eb6f-107">描述如何将自定义成员和值添加到 Visual Basic 中的 `My` 命名空间。</span><span class="sxs-lookup"><span data-stu-id="5eb6f-107">Describes how to add custom members and values to the `My` namespace in Visual Basic.</span></span>
- [<span data-ttu-id="5eb6f-108">打包和部署自定义 My 扩展</span><span class="sxs-lookup"><span data-stu-id="5eb6f-108">Packaging and Deploying Custom My Extensions</span></span>](packaging-and-deploying-custom-my-extensions.md)  
 <span data-ttu-id="5eb6f-109">介绍如何使用 Visual Studio 模板发布自定义 `My` 命名空间扩展。</span><span class="sxs-lookup"><span data-stu-id="5eb6f-109">Describes how to publish custom `My` namespace extensions by using Visual Studio templates.</span></span>
- [<span data-ttu-id="5eb6f-110">扩展 Visual Basic 应用程序模型</span><span class="sxs-lookup"><span data-stu-id="5eb6f-110">Extending the Visual Basic Application Model</span></span>](extending-the-visual-basic-application-model.md)  
 <span data-ttu-id="5eb6f-111">介绍如何通过重写 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase> 类的成员，为应用程序模型指定您自己的扩展。</span><span class="sxs-lookup"><span data-stu-id="5eb6f-111">Describes how to specify your own extensions to the application model by overriding members of the <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase> class.</span></span>
- [<span data-ttu-id="5eb6f-112">自定义 My 中可用的对象</span><span class="sxs-lookup"><span data-stu-id="5eb6f-112">Customizing Which Objects are Available in My</span></span>](customizing-which-objects-are-available-in-my.md)  
 <span data-ttu-id="5eb6f-113">介绍如何通过设置项目的 \_MYTYPE 条件编译常量来控制要启用的 `My` 对象。</span><span class="sxs-lookup"><span data-stu-id="5eb6f-113">Describes how to control which `My` objects are enabled by setting your project's \_MYTYPE conditional-compilation constant.</span></span>

## <a name="related-sections"></a><span data-ttu-id="5eb6f-114">相关章节</span><span class="sxs-lookup"><span data-stu-id="5eb6f-114">Related sections</span></span>

- [<span data-ttu-id="5eb6f-115">使用 My 开发</span><span class="sxs-lookup"><span data-stu-id="5eb6f-115">Development with My</span></span>](../development-with-my/index.md)  
 <span data-ttu-id="5eb6f-116">说明默认情况下，不同项目类型中可用的 `My` 对象。</span><span class="sxs-lookup"><span data-stu-id="5eb6f-116">Describes which `My` objects are available in different project types by default.</span></span>
- [<span data-ttu-id="5eb6f-117">Visual Basic 应用程序模型概述</span><span class="sxs-lookup"><span data-stu-id="5eb6f-117">Overview of the Visual Basic Application Model</span></span>](../development-with-my/overview-of-the-visual-basic-application-model.md)  
 <span data-ttu-id="5eb6f-118">介绍 Visual Basic 用于控制 Windows 窗体应用程序行为的模型。</span><span class="sxs-lookup"><span data-stu-id="5eb6f-118">Describes Visual Basic's model for controlling the behavior of Windows Forms applications.</span></span>
- [<span data-ttu-id="5eb6f-119">My 对项目类型的依赖方式</span><span class="sxs-lookup"><span data-stu-id="5eb6f-119">How My Depends on Project Type</span></span>](../development-with-my/how-my-depends-on-project-type.md)  
 <span data-ttu-id="5eb6f-120">说明默认情况下，不同项目类型中可用的 `My` 对象。</span><span class="sxs-lookup"><span data-stu-id="5eb6f-120">Describes which `My` objects are available in different project types by default.</span></span>
- [<span data-ttu-id="5eb6f-121">条件编译</span><span class="sxs-lookup"><span data-stu-id="5eb6f-121">Conditional Compilation</span></span>](../../programming-guide/program-structure/conditional-compilation.md)  
 <span data-ttu-id="5eb6f-122">讨论编译器如何使用条件编译来选择代码的特定部分，以便编译和排除其他部分。</span><span class="sxs-lookup"><span data-stu-id="5eb6f-122">Discusses how the compiler uses conditional-compilation to select particular sections of code to compile and exclude other sections.</span></span>
- <xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase>  
 <span data-ttu-id="5eb6f-123">介绍提供与当前应用程序相关的属性、方法和事件的 `My` 对象。</span><span class="sxs-lookup"><span data-stu-id="5eb6f-123">Describes the `My` object that provides properties, methods, and events related to the current application.</span></span>

## <a name="see-also"></a><span data-ttu-id="5eb6f-124">请参阅</span><span class="sxs-lookup"><span data-stu-id="5eb6f-124">See also</span></span>

- [<span data-ttu-id="5eb6f-125">使用 Visual Basic 开发应用程序</span><span class="sxs-lookup"><span data-stu-id="5eb6f-125">Developing Applications with Visual Basic</span></span>](../index.md)
