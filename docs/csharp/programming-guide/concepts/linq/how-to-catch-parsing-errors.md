---
title: 如何：捕捉分析错误 (C#)
ms.date: 07/20/2015
ms.assetid: bfb612d4-5605-48ef-8c93-915cf9d5dcfb
ms.openlocfilehash: 094485b24cdccee7898bd0344aa7c100e26bf4e9
ms.sourcegitcommit: 155012a8a826ee8ab6aa49b1b3a3b532e7b7d9bd
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/04/2019
ms.locfileid: "66487483"
---
# <a name="how-to-catch-parsing-errors-c"></a><span data-ttu-id="69253-102">如何：捕捉分析错误 (C#)</span><span class="sxs-lookup"><span data-stu-id="69253-102">How to: Catch Parsing Errors (C#)</span></span>
<span data-ttu-id="69253-103">本主题演示如何检测格式不正确或无效的 XML。</span><span class="sxs-lookup"><span data-stu-id="69253-103">This topic shows how to detect badly formed or invalid XML.</span></span>  
  
 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] <span data-ttu-id="69253-104">通过使用 <xref:System.Xml.XmlReader> 实现。</span><span class="sxs-lookup"><span data-stu-id="69253-104">is implemented using <xref:System.Xml.XmlReader>.</span></span> <span data-ttu-id="69253-105">如果将格式不正确或无效的 XML 传递给 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]，则基础 <xref:System.Xml.XmlReader> 类将引发异常。</span><span class="sxs-lookup"><span data-stu-id="69253-105">If badly formed or invalid XML is passed to [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)], the underlying <xref:System.Xml.XmlReader> class will throw an exception.</span></span> <span data-ttu-id="69253-106">用于分析 XML 的各种方法（如 <xref:System.Xml.Linq.XElement.Parse%2A?displayProperty=nameWithType>）不会捕捉异常；应用程序可以捕捉异常。</span><span class="sxs-lookup"><span data-stu-id="69253-106">The various methods that parse XML, such as <xref:System.Xml.Linq.XElement.Parse%2A?displayProperty=nameWithType>, do not catch the exception; the exception can then be caught by your application.</span></span>  
  
## <a name="example"></a><span data-ttu-id="69253-107">示例</span><span class="sxs-lookup"><span data-stu-id="69253-107">Example</span></span>  
 <span data-ttu-id="69253-108">下面的代码尝试分析无效的 XML：</span><span class="sxs-lookup"><span data-stu-id="69253-108">The following code tries to parse invalid XML:</span></span>  
  
```csharp  
try {  
    XElement contacts = XElement.Parse(  
        @"<Contacts>  
            <Contact>  
                <Name>Jim Wilson</Name>  
            </Contact>  
          </Contcts>");  
  
    Console.WriteLine(contacts);  
}  
catch (System.Xml.XmlException e)  
{  
    Console.WriteLine(e.Message);  
}  
```  
  
 <span data-ttu-id="69253-109">运行此代码时，会引发以下异常：</span><span class="sxs-lookup"><span data-stu-id="69253-109">When you run this code, it throws the following exception:</span></span>  
  
```  
The 'Contacts' start tag on line 1 does not match the end tag of 'Contcts'. Line 5, position 13.  
```  
  
 <span data-ttu-id="69253-110">有关 <xref:System.Xml.Linq.XElement.Parse%2A?displayProperty=nameWithType>、<xref:System.Xml.Linq.XDocument.Parse%2A?displayProperty=nameWithType>、<xref:System.Xml.Linq.XElement.Load%2A?displayProperty=nameWithType> 和 <xref:System.Xml.Linq.XDocument.Load%2A?displayProperty=nameWithType> 方法可能会引发的异常的更多信息，请参见 <xref:System.Xml.XmlReader> 文档。</span><span class="sxs-lookup"><span data-stu-id="69253-110">For information about the exceptions that you can expect the <xref:System.Xml.Linq.XElement.Parse%2A?displayProperty=nameWithType>, <xref:System.Xml.Linq.XDocument.Parse%2A?displayProperty=nameWithType>, <xref:System.Xml.Linq.XElement.Load%2A?displayProperty=nameWithType>, and <xref:System.Xml.Linq.XDocument.Load%2A?displayProperty=nameWithType> methods to throw, see the <xref:System.Xml.XmlReader> documentation.</span></span>  
  