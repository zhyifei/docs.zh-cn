---
title: 使用标准异常类型
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- throwing exceptions, standard types
- catching exceptions
- exceptions, catching
- exceptions, throwing
ms.assetid: ab22ce03-78f9-4dca-8824-c7ed3bdccc27
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9ea4a61be3a76c30c564cbf98ba3318fc6c3e7d4
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/26/2018
ms.locfileid: "47216090"
---
# <a name="using-standard-exception-types"></a>使用标准异常类型
本部分介绍框架提供的标准异常及其用法的详细信息。该清单并非详尽无遗。有关其他框架异常类型的用法，请参阅 .NET Framework 参考文档。  
  
## <a name="exception-and-systemexception"></a>Exception 和 SystemException
 **X 不要** 抛出<xref:System.Exception?displayProperty=nameWithType>或<xref:System.SystemException?displayProperty=nameWithType>。  
  
 **X 不要** 在框架代码中捕获 `System.Exception` 或 `System.SystemException` ，除非您想要重新抛出。  
  
 **X 避免** 捕获 `System.Exception` 或 `System.SystemException` ，顶级异常处理程序除外。 
  
## <a name="applicationexception"></a>ApplicationException
 **X 不要** 抛出或从<xref:System.ApplicationException>派生。  
  
## <a name="invalidoperationexception"></a>InvalidOperationException
 **✓ 务必** 抛出<xref:System.InvalidOperationException>，如果此对象处于不合适的状态。  
  
## <a name="argumentexception-argumentnullexception-and-argumentoutofrangeexception"></a>ArgumentException、 ArgumentNullException 和 ArgumentOutOfRangeException
**✓ 务必** 抛出<xref:System.ArgumentException>或其子类型之一，如果将错误的参数传递给成员。如果适用，首选使用派生程度最高的异常类型。
  
**✓ 务必** 在抛出 `ArgumentException` 的一个子类时，请设置 `ParamName` 属性。
  
此属性表示引发异常的参数的名称。 请注意，可以使用一个构造函数重载来设置该属性。
  
 **✓ 务必** 使用 `value` 作为属性 setter 的隐式值参数的名称。
  
## <a name="nullreferenceexception-indexoutofrangeexception-and-accessviolationexception"></a>NullReferenceException、 IndexOutOfRangeException 和 AccessViolationException
**X 不要** 允许公开可调用的 API 显式或隐式抛出<xref:System.NullReferenceException>， <xref:System.AccessViolationException>，或<xref:System.IndexOutOfRangeException>。这些异常由执行引擎保留和抛出，并且在大多数情况下表示错误。
  
应进行参数检查以避免抛出这些异常。抛出这些异常会暴露您的方法的实现细节，这些细节可能会随着时间而改变。
  
## <a name="stackoverflowexception"></a>StackOverflowException
**X 不要** 显式抛出<xref:System.StackOverflowException>。应仅由 CLR 显式抛出该异常。  
  
**X 不要** 捕获 `StackOverflowException`。

在存在任意堆栈溢出的情况下编写保持一致的托管代码几乎是不可能的。通过使用探针将堆栈溢出移动到明确定义的位置而不是从任意堆栈溢出中退出，CLR 的非托管部分可以保持一致。
  
## <a name="outofmemoryexception"></a>OutOfMemoryException
**X 不要** 显式抛出<xref:System.OutOfMemoryException>。应仅由 CLR 基础结构抛出此异常。  
  
## <a name="comexception-sehexception-and-executionengineexception"></a>ComException、 SEHException 和 ExecutionEngineException
**X 不要** 显式抛出<xref:System.Runtime.InteropServices.COMException>， <xref:System.ExecutionEngineException>，和<xref:System.Runtime.InteropServices.SEHException>。这些异常将仅由 CLR 基础结构抛出。  
  
*部分版权 © 2005, 2009 Microsoft Corporation。保留所有权利。*
  
*经 Pearson Education, Inc 授权，转载自《框架设计准则：可重用的 .NET 库的约定、习惯用语和模式，第2版》(https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) 作者：Krzysztof Cwalina 和 Brad Abrams，由 Addison Wesley Professional 于 2008 年 10 月 22 日印发，作为 Microsoft Windows 开发系列的一部分。*
  
## <a name="see-also"></a>请参阅

- [框架设计指南](../../../docs/standard/design-guidelines/index.md)  
- [异常的设计准则](../../../docs/standard/design-guidelines/exceptions.md)
