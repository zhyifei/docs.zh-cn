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
# <a name="how-to-parse-a-string-visual-basic"></a>如何：分析字符串 (Visual Basic)
本主题说明如何在中C#创建 XML 树。  
  
## <a name="example"></a>示例  
 您可以使用`XElement.Parse`方法分析 Visual Basic 中的字符串。 但是, 使用 XML 文本比使用 XML 文本更高效, 如以下代码所示, 因为 XML 文本与从字符串分析 XML 相比, 其性能会受到影响。  
  
 通过使用 XML 文本, 只需将 XML 复制并粘贴到 Visual Basic 程序中即可。  
  
> [!NOTE]
> 分析文本或从文本文件加载 XML 文档比函数构造的效率更低。 如果要从代码初始化 XML 树，使用函数构造比分析文本所占用的处理器时间更少。  
  
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
  
## <a name="see-also"></a>请参阅

- [分析 XML (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/parsing-xml.md)
