---
title: 自定义工作流设计体验
ms.date: 03/30/2017
helpviewer_keywords:
- extending [WF], Workflow Designer
ms.assetid: 98135077-0f5d-4d16-9337-01094e843537
ms.openlocfilehash: ed4ccb45e4470eb03cec856e865d4b50220816e3
ms.sourcegitcommit: 69229651598b427c550223d3c58aba82e47b3f82
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "48777534"
---
# <a name="customizing-the-workflow-design-experience"></a><span data-ttu-id="d2e21-102">自定义工作流设计体验</span><span class="sxs-lookup"><span data-stu-id="d2e21-102">Customizing the Workflow Design Experience</span></span>

<span data-ttu-id="d2e21-103">在 [!INCLUDE[wfd1](../../../includes/wfd1-md.md)] 中，已经对用于设计自定义活动以及重新承载 [!INCLUDE[netfx40_short](../../../includes/netfx40-short-md.md)] 的方案进行了大量简化。</span><span class="sxs-lookup"><span data-stu-id="d2e21-103">The scenarios for designing custom activities and for rehosting the [!INCLUDE[wfd1](../../../includes/wfd1-md.md)] have been greatly simplified in [!INCLUDE[netfx40_short](../../../includes/netfx40-short-md.md)].</span></span> <span data-ttu-id="d2e21-104">现在，开发和部署工作变得更轻松、更灵活。</span><span class="sxs-lookup"><span data-stu-id="d2e21-104">Development and deployment are now both easier and more flexible.</span></span> <span data-ttu-id="d2e21-105">主要的基础更改是新的活动设计器编程模型构建在 Windows Presentation Foundation (WPF)。</span><span class="sxs-lookup"><span data-stu-id="d2e21-105">The key infrastructural change is that the new activity designer programming model is built upon Windows Presentation Foundation (WPF).</span></span> <span data-ttu-id="d2e21-106">这使您能够以声明方式定义活动设计器，并且可以相当轻松地在其他应用程序中重新承载 [!INCLUDE[wfd2](../../../includes/wfd2-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="d2e21-106">This gives you the ability to define activity designers declaratively and to rehost the [!INCLUDE[wfd2](../../../includes/wfd2-md.md)] in other applications with comparative easy.</span></span> <span data-ttu-id="d2e21-107">在重新承载时，可以开发自定义表达式编辑器来支持 IntelliSense 或简化的表达式域。</span><span class="sxs-lookup"><span data-stu-id="d2e21-107">When rehosting, a custom expression editor can be developed to support IntelliSense or a simplified expression domain.</span></span> <span data-ttu-id="d2e21-108">使用 Windows Communication Foundation (WCF) 的集成已变得更加无缝使用工作流服务使用。</span><span class="sxs-lookup"><span data-stu-id="d2e21-108">The integration with Windows Communication Foundation (WCF) has become more seamless with use of workflow services.</span></span> <span data-ttu-id="d2e21-109">可使用自定义活动设计器和模型项树来增强重新承载的工作流设计器中的设计时体验。</span><span class="sxs-lookup"><span data-stu-id="d2e21-109">Custom activity designers and the Model Item Tree can be used to enhance design time experiences in rehosted workflow designers.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="d2e21-110">本节内容</span><span class="sxs-lookup"><span data-stu-id="d2e21-110">In This Section</span></span>

 [<span data-ttu-id="d2e21-111">使用自定义活动设计器和模板</span><span class="sxs-lookup"><span data-stu-id="d2e21-111">Using Custom Activity Designers and Templates</span></span>](../../../docs/framework/windows-workflow-foundation/using-custom-activity-designers-and-templates.md)

 <span data-ttu-id="d2e21-112">介绍如何创建新的自定义活动设计器和模板。</span><span class="sxs-lookup"><span data-stu-id="d2e21-112">Describes how to create new custom activity designers and templates.</span></span>

 [<span data-ttu-id="d2e21-113">重新托管工作流设计器</span><span class="sxs-lookup"><span data-stu-id="d2e21-113">Rehosting the Workflow Designer</span></span>](../../../docs/framework/windows-workflow-foundation/rehosting-the-workflow-designer.md)

 <span data-ttu-id="d2e21-114">介绍如何重新托管[!INCLUDE[wfd1](../../../includes/wfd1-md.md)]之外 Visual Studio 以及如何显示验证错误。</span><span class="sxs-lookup"><span data-stu-id="d2e21-114">Describes how to re-host the [!INCLUDE[wfd1](../../../includes/wfd1-md.md)] outside of Visual Studio and how to display validation errors.</span></span>

 [<span data-ttu-id="d2e21-115">使用自定义表达式编辑器</span><span class="sxs-lookup"><span data-stu-id="d2e21-115">Using a Custom Expression Editor</span></span>](../../../docs/framework/windows-workflow-foundation/using-a-custom-expression-editor.md)

 <span data-ttu-id="d2e21-116">介绍如何实现一个自定义表达式编辑器来使用 Visual Studio 2010 之外重新承载的工作流设计器。</span><span class="sxs-lookup"><span data-stu-id="d2e21-116">Describes how to implement a custom expression editor to use with workflow designers rehosted outside of Visual Studio 2010.</span></span>

## <a name="reference"></a><span data-ttu-id="d2e21-117">参考</span><span class="sxs-lookup"><span data-stu-id="d2e21-117">Reference</span></span>

<xref:System.Activities.Presentation.ActivityDesigner>

## <a name="see-also"></a><span data-ttu-id="d2e21-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="d2e21-118">See Also</span></span>

- [<span data-ttu-id="d2e21-119">扩展 Windows Workflow Foundation</span><span class="sxs-lookup"><span data-stu-id="d2e21-119">Extending Windows Workflow Foundation</span></span>](../../../docs/framework/windows-workflow-foundation/extend.md)
- [<span data-ttu-id="d2e21-120">设计器</span><span class="sxs-lookup"><span data-stu-id="d2e21-120">Designer</span></span>](../../../docs/framework/windows-workflow-foundation/samples/designer.md)
- [<span data-ttu-id="d2e21-121">自定义活动设计器</span><span class="sxs-lookup"><span data-stu-id="d2e21-121">Custom Activity Designers</span></span>](../../../docs/framework/windows-workflow-foundation/samples/custom-activity-designers.md)
- [<span data-ttu-id="d2e21-122">重新承载设计器</span><span class="sxs-lookup"><span data-stu-id="d2e21-122">Designer ReHosting</span></span>](../../../docs/framework/windows-workflow-foundation/samples/designer-rehosting.md)