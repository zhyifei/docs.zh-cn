---
title: "规划应用程序性能"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- applications [WPF], optimizing
- WPF application [WPF], optimizing
ms.assetid: c91bd0c5-a193-46ff-9da1-eb7a3a76a3b3
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: f47f56e28064c852e5d8f721bdb3a0f73172c12a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="planning-for-application-performance"></a>规划应用程序性能
达到性能目标成功取决于你开发你性能策略的程度。 规划是开发任何产品中的第一个阶段。 本主题介绍一些非常简单规则可用于开发良好的性能策略。  
  
## <a name="think-in-terms-of-scenarios"></a>考虑方案  
 方案可帮助你专注于你的应用程序的关键组件。 方案通常源自客户，以及竞争对手的产品。 始终研究客户，并找出实际产生它们非常高兴有关您的产品和竞争对手的产品。 你的客户的反馈可以帮助您确定应用程序的主要方案。 例如，如果你正在设计将在启动时使用的组件，则很可能，在应用程序启动时一次调用该组件。 启动时间变得关键方案。 重要的方案的其他示例可能是所需的帧速率对于动画序列，或最大工作集允许对应用程序。  
  
## <a name="define-goals"></a>定义目标  
 目标帮助你确定应用程序的性能速度更快或变慢。 应为每个方案定义目标。 你定义的所有性能目标应都基于客户预期。 它可能在应用程序开发在早期的目标重启，仍有许多解决的问题时制定性能比较困难。 但是，最好制定初始目标并晚于以目标根本没有修改它。  
  
## <a name="understand-your-platform"></a>了解你的平台  
 始终保持度量、 调查、 在应用程序开发周期中改进/更正的周期。 从开发周期的末尾开始，你需要测量可靠且稳定的环境中的应用程序的性能。 应避免通过外部因素造成的变化。 例如，测试性能时，你应禁用防病毒软件或如 SMS 任何自动更新，顺序不适用于影响性能测试结果。 一旦具有度量应用程序的性能，需要标识将导致最大的改进的更改。 一次修改了你的应用程序，再次启动该周期。  
  
## <a name="make-performance-tuning-an-iterative-process"></a>进行性能优化的迭代过程  
 您应该知道你将使用每个功能的相对成本。 例如，在中对反射的使用[!INCLUDE[TLA#tla_avalonwinfx](../../../../includes/tlasharptla-avalonwinfx-md.md)]通常是性能密集型根据计算资源，因此你将想要谨慎地使用。 这并不意味着若要避免使用反射，仅在你应小心地将其与你使用的功能的性能需求的应用程序性能要求相平衡。  
  
## <a name="build-towards-graphical-richness"></a>生成大量图形的内容  
 一种用于创建实现可缩放的方法的关键技术[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]应用程序性能是构建于图形丰富功能和复杂性。 始终使用最少的性能密集型资源实现方案目标开头。 后实现这些目标，请通过使用更多性能密集型功能，始终记住你方案的目标构建向图形丰富功能。 请记住，[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]是非常丰富的平台，并提供非常丰富的图形功能。 使用不加考虑性能密集型功能可以对应用程序总体性能产生负面影响。  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]控件是广泛的自定义其外观，而不修改其控件行为的从而本质上是可扩展。 通过利用的样式、 数据模板和控件模板，你可以创建并以增量方式不断发展可自定义[!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)]，适应性能要求。  
  
## <a name="see-also"></a>另请参阅  
 [优化 WPF 应用程序性能](../../../../docs/framework/wpf/advanced/optimizing-wpf-application-performance.md)  
 [利用硬件](../../../../docs/framework/wpf/advanced/optimizing-performance-taking-advantage-of-hardware.md)  
 [布局和示例](../../../../docs/framework/wpf/advanced/optimizing-performance-layout-and-design.md)  
 [2D 图形和图像处理](../../../../docs/framework/wpf/advanced/optimizing-performance-2d-graphics-and-imaging.md)  
 [对象行为](../../../../docs/framework/wpf/advanced/optimizing-performance-object-behavior.md)  
 [应用程序资源](../../../../docs/framework/wpf/advanced/optimizing-performance-application-resources.md)  
 [文本](../../../../docs/framework/wpf/advanced/optimizing-performance-text.md)  
 [数据绑定](../../../../docs/framework/wpf/advanced/optimizing-performance-data-binding.md)  
 [其他性能建议](../../../../docs/framework/wpf/advanced/optimizing-performance-other-recommendations.md)
