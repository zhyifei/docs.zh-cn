---
title: "自定义工作流设计体验"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: extending [WF], Workflow Designer
ms.assetid: 98135077-0f5d-4d16-9337-01094e843537
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 60e8d01ad32e10f06191f7e0b38dcb648780ba29
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2017
---
# <a name="customizing-the-workflow-design-experience"></a>自定义工作流设计体验
在 [!INCLUDE[wfd1](../../../includes/wfd1-md.md)] 中，已经对用于设计自定义活动以及重新承载 [!INCLUDE[netfx40_short](../../../includes/netfx40-short-md.md)] 的方案进行了大量简化。 现在，开发和部署工作变得更轻松、更灵活。 主要的基础更改是，新的活动设计器编程模型是基于 [!INCLUDE[avalon1](../../../includes/avalon1-md.md)] 构建的。 这使您能够以声明方式定义活动设计器，并且可以相当轻松地在其他应用程序中重新承载 [!INCLUDE[wfd2](../../../includes/wfd2-md.md)]。 在重新承载时，可以开发自定义表达式编辑器来支持 IntelliSense 或简化的表达式域。 通过使用工作流服务，与 [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] 的集成已变得更完美。 可使用自定义活动设计器和模型项树来增强重新承载的工作流设计器中的设计时体验。  
  
## <a name="in-this-section"></a>本节内容  
 [使用自定义活动设计器和模板](../../../docs/framework/windows-workflow-foundation/using-custom-activity-designers-and-templates.md)  
 介绍如何创建新的自定义活动设计器和模板。  
  
 [重新托管工作流设计器](../../../docs/framework/windows-workflow-foundation/rehosting-the-workflow-designer.md)  
 介绍如何在 [!INCLUDE[wfd1](../../../includes/wfd1-md.md)] 外部重新承载 [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] 以及如何显示验证错误。  
  
 [使用自定义表达式编辑器](../../../docs/framework/windows-workflow-foundation/using-a-custom-expression-editor.md)  
 介绍如何实现自定义表达式编辑器以用于在 [!INCLUDE[vs2010](../../../includes/vs2010-md.md)] 外部重新承载的工作流设计器。  
  
## <a name="reference"></a>参考  
 <xref:System.Activities.Presentation.ActivityDesigner>  
  
## <a name="see-also"></a>另请参阅  
 [扩展 Windows Workflow Foundation](../../../docs/framework/windows-workflow-foundation/extend.md)  
 [设计器](../../../docs/framework/windows-workflow-foundation/samples/designer.md)  
 [自定义活动设计器](../../../docs/framework/windows-workflow-foundation/samples/custom-activity-designers.md)  
 [重新承载设计器](../../../docs/framework/windows-workflow-foundation/samples/designer-rehosting.md)
