---
title: 如何： 分析字符串 (Visual Basic)
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 896e1b4b-f9bd-4975-8bc1-55b6badce1ac
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: d0fd7c7adcfbd7e2136d1a652017d470634016b9
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-parse-a-string-visual-basic"></a><span data-ttu-id="5a531-102">如何： 分析字符串 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5a531-102">How to: Parse a String (Visual Basic)</span></span>
<span data-ttu-id="5a531-103">本主题演示如何在 C# 中创建 XML 树。</span><span class="sxs-lookup"><span data-stu-id="5a531-103">This topic shows how to create an XML tree in C#.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5a531-104">示例</span><span class="sxs-lookup"><span data-stu-id="5a531-104">Example</span></span>  
 <span data-ttu-id="5a531-105">你可以通过分析在 Visual Basic 中的字符串`XElement.Parse`方法。</span><span class="sxs-lookup"><span data-stu-id="5a531-105">You can parse a string in Visual Basic by using the `XElement.Parse` method.</span></span> <span data-ttu-id="5a531-106">但是，它是使用 XML 文本，如下面的代码中所示，因为 XML 文本不会受到那样要牺牲性能从字符串分析 XML 那样更加高效。</span><span class="sxs-lookup"><span data-stu-id="5a531-106">However, it is more efficient to use XML literals, as shown in following code, because XML literals do not suffer from the same performance penalties as parsing XML from a string.</span></span>  
  
 <span data-ttu-id="5a531-107">通过使用 XML 文本，你可以复制和粘贴到你的 Visual Basic 程序的 XML。</span><span class="sxs-lookup"><span data-stu-id="5a531-107">By using XML literals, you can just copy and paste your XML into your Visual Basic program.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5a531-108">分析文本或从文本文件加载 XML 文档比函数构造的效率更低。</span><span class="sxs-lookup"><span data-stu-id="5a531-108">Parsing text or loading an XML document from a text file is less efficient than functional construction.</span></span> <span data-ttu-id="5a531-109">如果要从代码初始化 XML 树，使用函数构造比分析文本所占用的处理器时间更少。</span><span class="sxs-lookup"><span data-stu-id="5a531-109">If you are initializing an XML tree from code, it takes less processor time to use functional construction than to parse text.</span></span>  
  
```vb  
Dim contacts as XElement = _  
    <Contacts>  
        <Contact>  
            <Name>Patrick Hines</Name>  
            <Phone Type="home">206-555-0144</Phone>  
            <Phone Type="work">425-555-0145</Phone>  
            <Address>  
            <Street1>123 Main St</Street1>  
            <City>Mercer Island</City>  
            <State>WA</State>  
            <Postal>68042</Postal>  
            </Address>  
            <NetWorth>10</NetWorth>  
        </Contact>  
        <Contact>  
            <Name>Gretchen Rivas</Name>  
            <Phone Type="mobile">206-555-0163</Phone>  
            <Address>  
            <Street1>123 Main St</Street1>  
            <City>Mercer Island</City>  
            <State>WA</State>  
            <Postal>68042</Postal>  
            </Address>  
            <NetWorth>11</NetWorth>  
        </Contact>  
    </Contacts>  
```  
  
## <a name="see-also"></a><span data-ttu-id="5a531-110">请参阅</span><span class="sxs-lookup"><span data-stu-id="5a531-110">See Also</span></span>  
 [<span data-ttu-id="5a531-111">分析 XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5a531-111">Parsing XML (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/parsing-xml.md)
