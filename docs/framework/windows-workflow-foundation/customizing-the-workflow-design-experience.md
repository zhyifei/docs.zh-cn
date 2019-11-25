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
# <a name="customizing-the-workflow-design-experience"></a>自定义工作流设计体验

用于设计自定义活动和重新承载 [!INCLUDE[wfd1](../../../includes/wfd1-md.md)] 的方案在 .NET Framework 4 中已大大简化。 现在，开发和部署工作变得更轻松、更灵活。 关键的基础结构更改是，新的活动设计器编程模型是基于 Windows Presentation Foundation （WPF）构建的。 这使您能够以声明方式定义活动设计器，并且可以相当轻松地在其他应用程序中重新承载 [!INCLUDE[wfd2](../../../includes/wfd2-md.md)]。 在重新承载时，可以开发自定义表达式编辑器来支持 IntelliSense 或简化的表达式域。 使用工作流服务，可实现与 Windows Communication Foundation （WCF）的集成。 可使用自定义活动设计器和模型项树来增强重新承载的工作流设计器中的设计时体验。

## <a name="in-this-section"></a>本节内容

 [使用自定义活动设计器和模板](using-custom-activity-designers-and-templates.md)

 介绍如何创建新的自定义活动设计器和模板。

 [重新托管工作流设计器](rehosting-the-workflow-designer.md)

 介绍如何在 Visual Studio 外部重新承载 [!INCLUDE[wfd1](../../../includes/wfd1-md.md)] 以及如何显示验证错误。

 [使用自定义表达式编辑器](using-a-custom-expression-editor.md)

 介绍如何实现自定义表达式编辑器，以便在 Visual Studio 2010 之外的重新承载工作流设计器中使用。

## <a name="reference"></a>参考

<xref:System.Activities.Presentation.ActivityDesigner>

## <a name="see-also"></a>请参阅

- [扩展 Windows Workflow Foundation](extend.md)
- [设计器](./samples/designer.md)
- [自定义活动设计器](./samples/custom-activity-designers.md)
- [重新承载设计器](./samples/designer-rehosting.md)
