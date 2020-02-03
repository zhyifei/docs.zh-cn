---
title: 使用标准异常类型
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- throwing exceptions, standard types
- catching exceptions
- exceptions, catching
- exceptions, throwing
ms.assetid: ab22ce03-78f9-4dca-8824-c7ed3bdccc27
ms.openlocfilehash: 3caa94d9a39966614161e4b19201dcf6065776a2
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/24/2020
ms.locfileid: "76743541"
---
# <a name="using-standard-exception-types"></a>使用标准异常类型
本部分介绍 Framework 提供的标准异常及其用法的详细信息。 该列表并非详尽无遗。 有关其他 Framework 异常类型的用法，请参阅 .NET Framework 参考文档。

## <a name="exception-and-systemexception"></a>Exception 和 SystemException
 ❌ 不引发 <xref:System.Exception?displayProperty=nameWithType> 或 <xref:System.SystemException?displayProperty=nameWithType>。

 ❌ 不会在 framework 代码中捕获 `System.Exception` 或 `System.SystemException`，除非你打算重新引发。

 ❌ 避免捕获 `System.Exception` 或 `System.SystemException`，但在顶级异常处理程序中除外。

## <a name="applicationexception"></a>ApplicationException
 ❌ 不引发或派生自 <xref:System.ApplicationException>。

## <a name="invalidoperationexception"></a>InvalidOperationException
 如果对象处于不适当的状态，✔️会引发 <xref:System.InvalidOperationException>。

## <a name="argumentexception-argumentnullexception-and-argumentoutofrangeexception"></a>ArgumentException、ArgumentNullException 和 ArgumentOutOfRangeException
 如果向成员传递了错误的参数，✔️将引发 <xref:System.ArgumentException> 或其子类型之一。 如果适用，更喜欢派生程度最高的异常类型。

 ✔️在引发 `ArgumentException`的一个子类时设置 `ParamName` 属性。

 此属性表示引发异常的参数的名称。 请注意，可以使用一个构造函数重载来设置该属性。

 ✔️使用 `value` 作为属性 setter 的隐式值参数的名称。

## <a name="nullreferenceexception-indexoutofrangeexception-and-accessviolationexception"></a>NullReferenceException、IndexOutOfRangeException 和 AccessViolationException
 ❌ 不允许公共可调用 Api 显式或隐式引发 <xref:System.NullReferenceException>、<xref:System.AccessViolationException>或 <xref:System.IndexOutOfRangeException>。 这些异常由执行引擎保留并引发，在大多数情况下表示 bug。

 应检查参数以避免引发这些异常。 引发这些异常会暴露方法的实现细节，这些细节可能会随着时间而改变。

## <a name="stackoverflowexception"></a>StackOverflowException
 ❌ 不显式引发 <xref:System.StackOverflowException>。 异常只应由 CLR 显式引发。

 ❌ 不捕获 `StackOverflowException`。

 在存在任意堆栈溢出的情况下编写保持一致的托管代码几乎是不可能的。 通过使用探测功能将堆栈溢出移动到明确定义的位置而不是从任意堆栈溢出中退出，CLR 的非托管部分可以保持一致。

## <a name="outofmemoryexception"></a>OutOfMemoryException
 ❌ 不显式引发 <xref:System.OutOfMemoryException>。 此异常仅由 CLR 基础结构引发。

## <a name="comexception-sehexception-and-executionengineexception"></a>ComException、SEHException 和 ExecutionEngineException
 ❌ 不会显式引发 <xref:System.Runtime.InteropServices.COMException>、<xref:System.ExecutionEngineException>和 <xref:System.Runtime.InteropServices.SEHException>。 这些异常仅由 CLR 基础结构引发。

 *部分©2005，2009 Microsoft Corporation。保留所有权利。*

 *在 Pearson Education, Inc. 授权下，由 Addison-Wesley Professional 作为 Microsoft Windows 开发系列的一部分再版自 [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619)（Framework 设计准则：可重用 .NET 库的约定、惯例和模式第 2 版），由 Krzysztof Cwalina 和 Brad Abrams 发布于 2008 年 10 月 22 日。

## <a name="see-also"></a>另请参阅

- [框架设计指南](../../../docs/standard/design-guidelines/index.md)
- [异常的设计准则](../../../docs/standard/design-guidelines/exceptions.md)
