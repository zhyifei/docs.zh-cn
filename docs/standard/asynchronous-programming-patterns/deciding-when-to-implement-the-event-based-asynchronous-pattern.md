---
title: "确定何时实现基于事件的异步模式"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Event-based Asynchronous Pattern
- ProgressChangedEventArgs class
- BackgroundWorker component
- events [.NET Framework], asynchronous
- AsyncOperationManager class
- threading [.NET Framework], asynchronous features
- AsyncOperation class
- AsyncCompletedEventArgs class
ms.assetid: a00046aa-785d-4f7f-a8e5-d06475ea50da
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 48de1b736c251a61a2ad34975c77bc2bca139626
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="deciding-when-to-implement-the-event-based-asynchronous-pattern"></a>确定何时实现基于事件的异步模式
基于事件的异步模式公开异步行为的类提供的模式。 通过此模式中，引入[!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)]定义公开异步行为的两种模式： 基于异步模式<xref:System.IAsyncResult?displayProperty=nameWithType>接口，并且基于事件的模式。 本主题介绍当它适合于你要实现这两种模式。  
  
 有关使用异步编程的详细信息<xref:System.IAsyncResult>接口，请参阅[基于事件的异步模式 (EAP)](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-eap.md)。  
  
## <a name="general-principles"></a>一般原则  
 一般情况下，应公开使用基于事件的异步模式尽可能的异步功能。 但是，没有基于事件的模式不能满足某些要求。 在这些情况下，你可能需要实现<xref:System.IAsyncResult>除了基于事件的模式的模式。  
  
> [!NOTE]
>  很少<xref:System.IAsyncResult>模式，以实现没有还实现基于事件的模式。  
  
## <a name="guidelines"></a>准则  
 以下列表介绍应在何时实现基于事件的异步模式的准则：  
  
-   使用作为默认 API 基于事件的模式公开异步行为为您的类。  
  
-   不会公开<xref:System.IAsyncResult>模式时你类主要用于在客户端应用程序，例如 Windows 窗体。  
  
-   仅公开<xref:System.IAsyncResult>模式时才能满足你的要求。 例如，与现有 API 兼容性可能需要公开<xref:System.IAsyncResult>模式。  
  
-   不会公开<xref:System.IAsyncResult>模式而不会还公开基于事件的模式。  
  
-   如果必须公开<xref:System.IAsyncResult>模式，应将其作为一个高级选项。 例如，如果你生成一个代理对象，生成默认情况下，用于生成的选项的基于事件的模式<xref:System.IAsyncResult>模式。  
  
-   在上生成基于事件的模式实现你<xref:System.IAsyncResult>模式实现。  
  
-   避免将公开这两个基于事件的模式和<xref:System.IAsyncResult>同一类上的模式。 公开"更高级别的"类上的基于事件的模式和<xref:System.IAsyncResult>模式上的"降低级别"的类。 例如，将基于事件的模式上进行比较<xref:System.Net.WebClient>组件<xref:System.IAsyncResult>模式上<xref:System.Web.HttpRequest>类。  
  
    -   公开基于事件的模式和<xref:System.IAsyncResult>兼容性需要它时位于同一类上的模式。 例如，如果你已释放使用的 API<xref:System.IAsyncResult>模式中，你将需要保留<xref:System.IAsyncResult>向后兼容性模式。  
  
    -   公开基于事件的模式和<xref:System.IAsyncResult>模式同一类上，如果生成的对象模型复杂性超过带来的好处的分隔实现。 它是更好的做法公开比避免公开基于事件的模式单个类上的这两种模式。  
  
    -   如果你必须公开这两个基于事件的模式和<xref:System.IAsyncResult>上单个类，使用模式<xref:System.ComponentModel.EditorBrowsableAttribute>设置为<xref:System.ComponentModel.EditorBrowsableState.Advanced>标记<xref:System.IAsyncResult>模式实现作为一项高级功能。 这将指示设计环境中，如[!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)]IntelliSense，不希望显示<xref:System.IAsyncResult>属性和方法。 这些属性和方法仍将完全不可用，但通过 IntelliSense 工作的开发人员可以更加清晰的视图的 api。  
  
## <a name="criteria-for-exposing-the-iasyncresult-pattern-in-addition-to-the-event-based-pattern"></a>用于公开 IAsyncResult 模式除了基于事件的模式的条件  
 虽然基于事件的异步模式有许多好处，前面所述的情况下，它具有某些缺点，你应注意如果性能是您最重要的要求。  
  
 有三种基于事件的模式不能解决的方案以及<xref:System.IAsyncResult>模式：  
  
-   阻止，正在等待上一个<xref:System.IAsyncResult>  
  
-   阻止正在等待多个<xref:System.IAsyncResult>对象  
  
-   轮询上完成<xref:System.IAsyncResult>  
  
 你可以通过使用基于事件的模式，来满足这些方案，但这种比较麻烦比使用<xref:System.IAsyncResult>模式。  
  
 开发人员通常使用<xref:System.IAsyncResult>对于通常具有非常高的性能要求的服务的模式。 例如，对完成情形轮询是高性能服务器技术。  
  
 此外，基于事件的模式是效率低于<xref:System.IAsyncResult>模式，因为它会创建更多的对象，尤其是<xref:System.EventArgs>，而是因为它将同步的线程。  
  
 以下列表显示了一些建议，如果你决定使用，请按照<xref:System.IAsyncResult>模式：  
  
-   仅公开<xref:System.IAsyncResult>模式时特别需要支持<xref:System.Threading.WaitHandle>或<xref:System.IAsyncResult>对象。  
  
-   仅公开<xref:System.IAsyncResult>模式时必须使用的现有 API<xref:System.IAsyncResult>模式。  
  
-   如果你有现有 API 基于<xref:System.IAsyncResult>模式，请考虑也公开在下一个版本中的基于事件的模式。  
  
-   仅公开<xref:System.IAsyncResult>如果你有高性能要求的已验证的模式不满足由基于事件的模式，但它可以通过满足<xref:System.IAsyncResult>模式。  
  
## <a name="see-also"></a>另请参阅  
 [演练：实现支持基于事件的异步模式的组件](../../../docs/standard/asynchronous-programming-patterns/component-that-supports-the-event-based-asynchronous-pattern.md)  
 [基于事件的异步模式 (EAP)](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-eap.md)  
 [使用基于事件的异步模式进行多线程编程](../../../docs/standard/asynchronous-programming-patterns/multithreaded-programming-with-the-event-based-asynchronous-pattern.md)  
 [实现基于事件的异步模式](../../../docs/standard/asynchronous-programming-patterns/implementing-the-event-based-asynchronous-pattern.md)  
 [实现基于事件的异步模式的最佳做法](../../../docs/standard/asynchronous-programming-patterns/best-practices-for-implementing-the-event-based-asynchronous-pattern.md)  
 [基于事件的异步模式概述](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md)
