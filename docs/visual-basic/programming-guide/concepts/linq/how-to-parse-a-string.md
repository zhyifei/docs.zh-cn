---
title: "如何： 分析字符串 (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 896e1b4b-f9bd-4975-8bc1-55b6badce1ac
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 10b80c72cae70437ff812c4b67b2532d708f1e69
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-parse-a-string-visual-basic"></a><span data-ttu-id="2b870-102">如何： 分析字符串 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2b870-102">How to: Parse a String (Visual Basic)</span></span>
<span data-ttu-id="2b870-103">本主题演示如何在 C# 中创建 XML 树。</span><span class="sxs-lookup"><span data-stu-id="2b870-103">This topic shows how to create an XML tree in C#.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2b870-104">示例</span><span class="sxs-lookup"><span data-stu-id="2b870-104">Example</span></span>  
 <span data-ttu-id="2b870-105">你可以分析中的字符串[!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]使用`XElement.Parse`方法。</span><span class="sxs-lookup"><span data-stu-id="2b870-105">You can parse a string in [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] by using the `XElement.Parse` method.</span></span> <span data-ttu-id="2b870-106">但是，它是使用 XML 文本，如下面的代码中所示，因为 XML 文本不会受到那样要牺牲性能从字符串分析 XML 那样更加高效。</span><span class="sxs-lookup"><span data-stu-id="2b870-106">However, it is more efficient to use XML literals, as shown in following code, because XML literals do not suffer from the same performance penalties as parsing XML from a string.</span></span>  
  
 <span data-ttu-id="2b870-107">通过使用 XML 文本，可以将 XML 复制和粘贴到 [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] 程序中。</span><span class="sxs-lookup"><span data-stu-id="2b870-107">By using XML literals, you can just copy and paste your XML into your [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] program.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2b870-108">分析文本或从文本文件加载 XML 文档比函数构造的效率更低。</span><span class="sxs-lookup"><span data-stu-id="2b870-108">Parsing text or loading an XML document from a text file is less efficient than functional construction.</span></span> <span data-ttu-id="2b870-109">如果要从代码初始化 XML 树，使用函数构造比分析文本所占用的处理器时间更少。</span><span class="sxs-lookup"><span data-stu-id="2b870-109">If you are initializing an XML tree from code, it takes less processor time to use functional construction than to parse text.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="2b870-110">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2b870-110">See Also</span></span>  
 [<span data-ttu-id="2b870-111">分析 XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2b870-111">Parsing XML (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/parsing-xml.md)
