---
title: 异常类和属性
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- exceptions, Exception class
- Exception class
ms.assetid: e2e1f8c4-e7b4-467d-9a66-13c90861221d
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 9cdc464234871fc07feeeb8dd02635ebdd151d76
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33573114"
---
# <a name="exception-class-and-properties"></a><span data-ttu-id="423a2-102">异常类和属性</span><span class="sxs-lookup"><span data-stu-id="423a2-102">Exception class and properties</span></span>

<span data-ttu-id="423a2-103"><xref:System.Exception> 类是异常从中继承的基类。</span><span class="sxs-lookup"><span data-stu-id="423a2-103">The <xref:System.Exception> class is the base class from which exceptions inherit.</span></span> <span data-ttu-id="423a2-104">例如，<xref:System.InvalidCastException> 类层次结构如下所示：</span><span class="sxs-lookup"><span data-stu-id="423a2-104">For example, the <xref:System.InvalidCastException> class hierarchy is as follows:</span></span>

```
Object
  Exception
    SystemException
       InvalidCastException
```

<span data-ttu-id="423a2-105"><xref:System.Exception> 类具有以下属性，有助于更轻松地理解异常。</span><span class="sxs-lookup"><span data-stu-id="423a2-105">The <xref:System.Exception> class has the following properties that help make understanding an exception easier.</span></span>

| <span data-ttu-id="423a2-106">属性名</span><span class="sxs-lookup"><span data-stu-id="423a2-106">Property Name</span></span> | <span data-ttu-id="423a2-107">描述</span><span class="sxs-lookup"><span data-stu-id="423a2-107">Description</span></span> |
| ------------- | ----------- |
| <xref:System.Exception.Data> | <span data-ttu-id="423a2-108"><xref:System.Collections.IDictionary> 包含键/值对中的任意数据。</span><span class="sxs-lookup"><span data-stu-id="423a2-108">An <xref:System.Collections.IDictionary> that holds arbitrary data in key-value pairs.</span></span> |
| <xref:System.Exception.HelpLink> | <span data-ttu-id="423a2-109">可容纳指向帮助文件的 URL（或 URN），帮助文件中提供了大量信息说明了异常的原因。</span><span class="sxs-lookup"><span data-stu-id="423a2-109">Can hold a URL (or URN) to a help file that provides extensive information about the cause of an exception.</span></span> |
| <xref:System.Exception.InnerException> | <span data-ttu-id="423a2-110">在处理异常时此属性可用于创建和保留一系列异常。</span><span class="sxs-lookup"><span data-stu-id="423a2-110">This property can be used to create and preserve a series of exceptions during exception handling.</span></span> <span data-ttu-id="423a2-111">可将其用于创建新异常，其中包含之前捕获到的异常。</span><span class="sxs-lookup"><span data-stu-id="423a2-111">You can use it to create a new exception that contains previously caught exceptions.</span></span> <span data-ttu-id="423a2-112">可通过 <xref:System.Exception.InnerException> 属性中的第二个异常捕获原始异常，允许处理第二个异常的代码检查其他信息。</span><span class="sxs-lookup"><span data-stu-id="423a2-112">The original exception can be captured by the second exception in the <xref:System.Exception.InnerException> property, allowing code that handles the second exception to examine the additional information.</span></span> <span data-ttu-id="423a2-113">例如，假设有一个方法可接收格式不正确的参数。</span><span class="sxs-lookup"><span data-stu-id="423a2-113">For example, suppose you have a method that receives an argument that's improperly formatted.</span></span>  <span data-ttu-id="423a2-114">该代码尝试读取参数，但会引发异常。</span><span class="sxs-lookup"><span data-stu-id="423a2-114">The code tries to read the argument, but an exception is thrown.</span></span> <span data-ttu-id="423a2-115">该方法会捕获异常并引发 <xref:System.FormatException>。</span><span class="sxs-lookup"><span data-stu-id="423a2-115">The method catches the exception and throws a <xref:System.FormatException>.</span></span> <span data-ttu-id="423a2-116">若要提高调用方确定引发异常的原因的能力，有时最好用一个方法捕获帮助器例程引发的异常，然后引发一个更能说明已发生错误的异常。</span><span class="sxs-lookup"><span data-stu-id="423a2-116">To improve the caller's ability to determine the reason an exception is thrown, it is sometimes desirable for a method to catch an exception thrown by a helper routine and then throw an exception more indicative of the error that has occurred.</span></span> <span data-ttu-id="423a2-117">可创建一个新的且更有意义的异常，其中可将内部异常引用设为原始异常。</span><span class="sxs-lookup"><span data-stu-id="423a2-117">A new and more meaningful exception can be created, where the inner exception reference can be set to the original exception.</span></span> <span data-ttu-id="423a2-118">然后可向调用方引发此更有意义的异常。</span><span class="sxs-lookup"><span data-stu-id="423a2-118">This more meaningful exception can then be thrown to the caller.</span></span> <span data-ttu-id="423a2-119">请注意，使用此功能，可创建一系列链接的异常，以最先引发的异常结尾。</span><span class="sxs-lookup"><span data-stu-id="423a2-119">Note that with this functionality, you can create a series of linked exceptions that ends with the exception that was thrown first.</span></span> |
| <xref:System.Exception.Message> | <span data-ttu-id="423a2-120">提供有关异常原因的详细信息。</span><span class="sxs-lookup"><span data-stu-id="423a2-120">Provides details about the cause of an exception.</span></span>
| <xref:System.Exception.Source> | <span data-ttu-id="423a2-121">获取或设置导致错误的应用程序或对象的名称。</span><span class="sxs-lookup"><span data-stu-id="423a2-121">Gets or sets the name of the application or the object that causes the error.</span></span> |
| <xref:System.Exception.StackTrace>| <span data-ttu-id="423a2-122">包含可用于确定错误位置的堆栈跟踪。</span><span class="sxs-lookup"><span data-stu-id="423a2-122">Contains a stack trace that can be used to determine where an error occurred.</span></span> <span data-ttu-id="423a2-123">如果有可用的调试信息，则堆栈跟踪包含源文件名和程序行号。</span><span class="sxs-lookup"><span data-stu-id="423a2-123">The stack trace includes the source file name and program line number if debugging information is available.</span></span> |

<span data-ttu-id="423a2-124">继承自 <xref:System.Exception> 的大多数类无法实现其他成员或提供其他功能；它们只从 <xref:System.Exception> 进行继承。</span><span class="sxs-lookup"><span data-stu-id="423a2-124">Most of the classes that inherit from <xref:System.Exception> do not implement additional members or provide additional functionality; they simply inherit from <xref:System.Exception>.</span></span> <span data-ttu-id="423a2-125">因此，可在异常类层次结构、异常名称和异常所含的信息中找到异常的重要信息。</span><span class="sxs-lookup"><span data-stu-id="423a2-125">Therefore, the most important information for an exception can be found in the hierarchy of exception classes, the exception name, and the information contained in the exception.</span></span>

<span data-ttu-id="423a2-126">建议仅抛出和捕获派生自 <xref:System.Exception> 的对象，但可以将派生自 <xref:System.Object> 类的任何对象作为异常抛出。</span><span class="sxs-lookup"><span data-stu-id="423a2-126">We recommend that you throw and catch only objects that derive from <xref:System.Exception>, but you can throw any object that derives from the <xref:System.Object> class as an exception.</span></span> <span data-ttu-id="423a2-127">请注意，并非所有语言都支持引发和捕获不是从 <xref:System.Exception> 派生的对象。</span><span class="sxs-lookup"><span data-stu-id="423a2-127">Note that not all languages support throwing and catching objects that do not derive from <xref:System.Exception>.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="423a2-128">请参阅</span><span class="sxs-lookup"><span data-stu-id="423a2-128">See Also</span></span>  
[<span data-ttu-id="423a2-129">异常</span><span class="sxs-lookup"><span data-stu-id="423a2-129">Exceptions</span></span>](index.md)
