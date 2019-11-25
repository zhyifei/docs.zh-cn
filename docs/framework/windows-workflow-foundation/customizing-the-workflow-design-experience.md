---
title: 自定义工作流设计体验
ms.date: 03/30/2017
helpviewer_keywords:
- extending [WF], Workflow Designer
ms.assetid: 98135077-0f5d-4d16-9337-01094e843537
ms.openlocfilehash: 41be55391ae9481f6c2e4feb76443f7fb676b69d
ms.sourcegitcommit: fbb8a593a511ce667992502a3ce6d8f65c594edf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/16/2019
ms.locfileid: "74141923"
---
# <a name="customizing-the-workflow-design-experience"></a><span data-ttu-id="e59f6-102">自定义工作流设计体验</span><span class="sxs-lookup"><span data-stu-id="e59f6-102">Customizing the Workflow Design Experience</span></span>

<span data-ttu-id="e59f6-103">用于设计自定义活动和重新承载 [!INCLUDE[wfd1](../../../includes/wfd1-md.md)] 的方案在 .NET Framework 4 中已大大简化。</span><span class="sxs-lookup"><span data-stu-id="e59f6-103">The scenarios for designing custom activities and for rehosting the [!INCLUDE[wfd1](../../../includes/wfd1-md.md)] have been greatly simplified in .NET Framework 4.</span></span> <span data-ttu-id="e59f6-104">现在，开发和部署工作变得更轻松、更灵活。</span><span class="sxs-lookup"><span data-stu-id="e59f6-104">Development and deployment are now both easier and more flexible.</span></span> <span data-ttu-id="e59f6-105">关键的基础结构更改是，新的活动设计器编程模型是基于 Windows Presentation Foundation （WPF）构建的。</span><span class="sxs-lookup"><span data-stu-id="e59f6-105">The key infrastructural change is that the new activity designer programming model is built upon Windows Presentation Foundation (WPF).</span></span> <span data-ttu-id="e59f6-106">这使您能够以声明方式定义活动设计器，并且可以相当轻松地在其他应用程序中重新承载 [!INCLUDE[wfd2](../../../includes/wfd2-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="e59f6-106">This gives you the ability to define activity designers declaratively and to rehost the [!INCLUDE[wfd2](../../../includes/wfd2-md.md)] in other applications with comparative easy.</span></span> <span data-ttu-id="e59f6-107">在重新承载时，可以开发自定义表达式编辑器来支持 IntelliSense 或简化的表达式域。</span><span class="sxs-lookup"><span data-stu-id="e59f6-107">When rehosting, a custom expression editor can be developed to support IntelliSense or a simplified expression domain.</span></span> <span data-ttu-id="e59f6-108">使用工作流服务，可实现与 Windows Communication Foundation （WCF）的集成。</span><span class="sxs-lookup"><span data-stu-id="e59f6-108">The integration with Windows Communication Foundation (WCF) has become more seamless with use of workflow services.</span></span> <span data-ttu-id="e59f6-109">可使用自定义活动设计器和模型项树来增强重新承载的工作流设计器中的设计时体验。</span><span class="sxs-lookup"><span data-stu-id="e59f6-109">Custom activity designers and the Model Item Tree can be used to enhance design time experiences in rehosted workflow designers.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="e59f6-110">本节内容</span><span class="sxs-lookup"><span data-stu-id="e59f6-110">In This Section</span></span>

 [<span data-ttu-id="e59f6-111">使用自定义活动设计器和模板</span><span class="sxs-lookup"><span data-stu-id="e59f6-111">Using Custom Activity Designers and Templates</span></span>](using-custom-activity-designers-and-templates.md)

 <span data-ttu-id="e59f6-112">介绍如何创建新的自定义活动设计器和模板。</span><span class="sxs-lookup"><span data-stu-id="e59f6-112">Describes how to create new custom activity designers and templates.</span></span>

 [<span data-ttu-id="e59f6-113">重新托管工作流设计器</span><span class="sxs-lookup"><span data-stu-id="e59f6-113">Rehosting the Workflow Designer</span></span>](rehosting-the-workflow-designer.md)

 <span data-ttu-id="e59f6-114">介绍如何在 Visual Studio 外部重新承载 [!INCLUDE[wfd1](../../../includes/wfd1-md.md)] 以及如何显示验证错误。</span><span class="sxs-lookup"><span data-stu-id="e59f6-114">Describes how to re-host the [!INCLUDE[wfd1](../../../includes/wfd1-md.md)] outside of Visual Studio and how to display validation errors.</span></span>

 [<span data-ttu-id="e59f6-115">使用自定义表达式编辑器</span><span class="sxs-lookup"><span data-stu-id="e59f6-115">Using a Custom Expression Editor</span></span>](using-a-custom-expression-editor.md)

 <span data-ttu-id="e59f6-116">介绍如何实现自定义表达式编辑器，以便在 Visual Studio 2010 之外的重新承载工作流设计器中使用。</span><span class="sxs-lookup"><span data-stu-id="e59f6-116">Describes how to implement a custom expression editor to use with workflow designers rehosted outside of Visual Studio 2010.</span></span>

## <a name="reference"></a><span data-ttu-id="e59f6-117">参考</span><span class="sxs-lookup"><span data-stu-id="e59f6-117">Reference</span></span>

<xref:System.Activities.Presentation.ActivityDesigner>

## <a name="see-also"></a><span data-ttu-id="e59f6-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="e59f6-118">See also</span></span>

- [<span data-ttu-id="e59f6-119">扩展 Windows Workflow Foundation</span><span class="sxs-lookup"><span data-stu-id="e59f6-119">Extending Windows Workflow Foundation</span></span>](extend.md)
- [<span data-ttu-id="e59f6-120">设计器</span><span class="sxs-lookup"><span data-stu-id="e59f6-120">Designer</span></span>](./samples/designer.md)
- [<span data-ttu-id="e59f6-121">自定义活动设计器</span><span class="sxs-lookup"><span data-stu-id="e59f6-121">Custom Activity Designers</span></span>](./samples/custom-activity-designers.md)
- [<span data-ttu-id="e59f6-122">重新承载设计器</span><span class="sxs-lookup"><span data-stu-id="e59f6-122">Designer ReHosting</span></span>](./samples/designer-rehosting.md)
