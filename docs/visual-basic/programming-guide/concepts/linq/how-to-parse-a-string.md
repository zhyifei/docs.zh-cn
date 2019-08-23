---
title: 如何：分析字符串 (Visual Basic)
ms.date: 07/20/2015
ms.assetid: 896e1b4b-f9bd-4975-8bc1-55b6badce1ac
ms.openlocfilehash: b97ce93c1018ec48649ab8b259d5f1a07109b9fe
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69956379"
---
# <a name="how-to-parse-a-string-visual-basic"></a><span data-ttu-id="2aab6-102">如何：分析字符串 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2aab6-102">How to: Parse a String (Visual Basic)</span></span>
<span data-ttu-id="2aab6-103">本主题说明如何在中C#创建 XML 树。</span><span class="sxs-lookup"><span data-stu-id="2aab6-103">This topic shows how to create an XML tree in C#.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2aab6-104">示例</span><span class="sxs-lookup"><span data-stu-id="2aab6-104">Example</span></span>  
 <span data-ttu-id="2aab6-105">您可以使用`XElement.Parse`方法分析 Visual Basic 中的字符串。</span><span class="sxs-lookup"><span data-stu-id="2aab6-105">You can parse a string in Visual Basic by using the `XElement.Parse` method.</span></span> <span data-ttu-id="2aab6-106">但是, 使用 XML 文本比使用 XML 文本更高效, 如以下代码所示, 因为 XML 文本与从字符串分析 XML 相比, 其性能会受到影响。</span><span class="sxs-lookup"><span data-stu-id="2aab6-106">However, it is more efficient to use XML literals, as shown in following code, because XML literals do not suffer from the same performance penalties as parsing XML from a string.</span></span>  
  
 <span data-ttu-id="2aab6-107">通过使用 XML 文本, 只需将 XML 复制并粘贴到 Visual Basic 程序中即可。</span><span class="sxs-lookup"><span data-stu-id="2aab6-107">By using XML literals, you can just copy and paste your XML into your Visual Basic program.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="2aab6-108">分析文本或从文本文件加载 XML 文档比函数构造的效率更低。</span><span class="sxs-lookup"><span data-stu-id="2aab6-108">Parsing text or loading an XML document from a text file is less efficient than functional construction.</span></span> <span data-ttu-id="2aab6-109">如果要从代码初始化 XML 树，使用函数构造比分析文本所占用的处理器时间更少。</span><span class="sxs-lookup"><span data-stu-id="2aab6-109">If you are initializing an XML tree from code, it takes less processor time to use functional construction than to parse text.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="2aab6-110">请参阅</span><span class="sxs-lookup"><span data-stu-id="2aab6-110">See also</span></span>

- [<span data-ttu-id="2aab6-111">分析 XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2aab6-111">Parsing XML (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/parsing-xml.md)
