---
title: "错误处理"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c948841a-7db9-40ae-9b78-587d216cbcaf
caps.latest.revision: "3"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 308712ed4c8f44740622c57525f152152f7d6c73
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="error-handling"></a>错误处理
## <a name="error-handling-in-windows-communication-foundation"></a>Windows Communication Foundation 中的错误处理  
 在某一服务遇到意外的异常或错误时，有多种方式可以设计异常处理解决方案。 尽管不不存在任何单一的"正确"最佳做法"错误处理解决方案，有多种有效途径可供考虑。 通常建议实现混合解决方案将从下表，具体取决于 WCF 实现、 类型和频率的异常，处理复杂的多个方法与未处理性质组合在一起异常和任何关联的跟踪、 日志记录或策略要求。  
  
 在本节的其余部分中将更深入地说明这些解决方案。  
  
### <a name="the-microsoft-enterprise-library"></a>Microsoft 企业库  
 Microsoft 企业库异常处理应用程序块帮助实现常见的设计模式并且创建一致的策略，以便处理在企业应用程序的所有体系结构层中出现的异常。 它设计为支持在应用程序组件的 Catch 语句中包含的典型代码。 借助于该异常处理应用程序块，开发人员能够将该逻辑作为可重复使用的异常处理程序进行封装，而不必在应用程序的完全相同的 catch 块中重复此代码（例如将异常信息记入日志的代码）。  
  
 该库包含现成的错误协定异常处理程序。 该异常处理程序是为在 Windows® Communication Foundation (WCF) 服务边界使用而设计的，并且根据异常生成新的错误协定。  
  
 应用程序块旨在纳入常用的最佳做法并且为应用程序中的异常处理提供一般的方法。 另一方面，自定义的错误处理程序以及自己开发的错误协定也可能非常有用。 例如，自定义错误处理程序提供了一个很好的机会以便将自动提升到 Faultexception 的所有异常，以及将日志记录功能添加到你的应用程序。  
  
 有关详细信息，请参阅[Microsoft Enterprise Library](http://msdn.microsoft.com/library/ff632023.aspx)。  
  
### <a name="dealing-with-expected-exceptions"></a>处理预期异常  
 正确的操作过程是捕获预期的异常在每个操作或相关扩展点，确定它们是否可以恢复，并在 FaultException 中返回正确的自定义错误\<T >  
  
### <a name="dealing-with-unexpected-exceptions-using-an-ierrorhandler"></a>使用 IErrorHandler 处理意外的异常  
 为了应对意外的异常，建议过程是操作的"挂钩"IErrorHandler。 在 WCF 运行时级别 （"服务模型"层），而不是在通道层，错误处理程序仅捕获异常。 在通道层挂钩 IErrorHandler 的唯一方法是创建一个自定义通道，但在大多数情况下不建议这样做。  
  
 "意外的异常"通常是既不不可恢复异常，也不处理异常;它是，相反，一个意外的用户异常。 不可恢复异常 （例如内存不足异常） – 通常由[服务模型异常处理程序](http://msdn.microsoft.com/library/system.servicemodel.dispatcher.exceptionhandler.aspx)自动 – 不通常能处理正常，和的唯一原因来处理此类异常在所有可能执行其他日志记录或若要将标准异常返回到客户端。 在处理消息的过程中（例如，在序列化、编码器或格式化程序级别）发生的处理异常不能在 IErrorHandler 进行处理，因为就发生这些异常的时间而言，错误处理程序介入的时间要么过早，要么过晚。 同样，不能在 IErrorHandler 处理传输异常。  
  
 使用 IErrorHandler，您可以显式控制某一异常引发时您的应用程序的行为。 您可以：  
  
1.  确定是否将错误发送到客户端  
  
2.  使用错误替代异常  
  
3.  使用另一个错误替代错误  
  
4.  执行日志记录或跟踪  
  
5.  执行其他自定义活动  
  
 可通过将自定义错误处理程序添加到您的服务的通道调度程序的 ErrorHandlers 属性，安装该错误处理程序。  可以具有多个错误处理程序，并且按照将这些错误处理程序添加到该集合的顺序调用它们。  
  
 IErrorHandler.ProvideFault 控制发送到客户端的错误消息。 无论您的服务中的操作所引发的是何种异常类型，都会调用此方法。 如果在这里未执行任何操作，WCF 会假定采用其默认行为，并且就像没有任何自定义错误处理程序一样继续操作。  
  
 您可能会使用此方法的一个方面是在您想要创建一个中心位置以便在将异常发送到客户端之前将异常转换为错误时（确保实例不会被释放并且通道不会转移到错误状态）。  
  
 IErrorHandler.HandleError 方法通常用来实现错误相关行为，例如错误日志记录、系统通知、关闭应用程序等。可以在服务内的多个地方调用 IErrorHandler.HandleError，并且根据引发错误的位置，HandleError 方法不一定被与操作相同的线程调用；在此方面不作任何保证。  
  
### <a name="dealing-with-exceptions-outside-wcf"></a>处理 WCF 外的异常  
 配置异常、数据库连接字符串异常以及其他类似异常经常可能会在 WCF 应用程序环境内发生，但它们本身不是服务模型或 Web 服务本身导致的异常。 这些异常是 web 服务外部的"常规"异常，并且应将处理在环境中的其他外部异常一样处理。  
  
### <a name="tracing-exceptions"></a>跟踪异常  
 跟踪是其中一个可能能够看到所有异常的仅"全部捕捉"位置。 有关跟踪和日志记录异常的更多信息，请参见“跟踪和日志记录”。  
  
### <a name="uri-template-errors-when-using-webgetattribute-and-webinvokeattribute"></a>使用 WebGetAttribute 和 WebInvokeAttribute 时的 URI 模板错误  
 通过 WebGet 和 WebInvoke 特性，您可以指定将请求地址的组件映射到操作参数的 URI 模板。 例如，URI 模板“weather/{state}/{city}”将请求地址映射到文本标记、名为 state 的参数和名为 city 的参数。 然后，可以将这些参数按名称绑定到该操作的某些形参上。  
  
 模板参数在 URI 内以字符串的形式出现，而类型化协定的形参可能属于非字符串类型。 因此，需要进行某种转换，才能调用该操作。 A[转换格式表](http://msdn.microsoft.com/library/bb412172.aspx)可用。  
  
 但是，如果转换失败，则无法让该操作知道出现了问题。 类型转换而是以调度失败的形式出现。  
  
 可通过安装错误处理程序，像许多其他类型的调度失败一样检查类型转换调度失败。 调用 IErrorHandler 扩展点处理服务级别异常。 从中，可以选择要发送回调用方的响应，以及执行任何自定义任务和报告。  
  
## <a name="see-also"></a>另请参阅  
 [基本 WCF 错误处理](http://msdn.microsoft.com/library/gg281715.aspx)
