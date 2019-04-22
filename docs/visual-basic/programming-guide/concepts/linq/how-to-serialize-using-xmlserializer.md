---
title: 如何：序列化使用 XmlSerializer (Visual Basic)
ms.date: 07/20/2015
ms.assetid: cace24eb-0f43-4016-8e4b-199e5ef73a1c
ms.openlocfilehash: 1799ef4a0d0f20cddc4514c9dc901047c631b158
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "58821460"
---
# <a name="how-to-serialize-using-xmlserializer-visual-basic"></a><span data-ttu-id="9e3a1-102">如何：序列化使用 XmlSerializer (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9e3a1-102">How to: Serialize Using XmlSerializer (Visual Basic)</span></span>
<span data-ttu-id="9e3a1-103">本主题显示一个使用 <xref:System.Xml.Serialization.XmlSerializer> 进行序列化和反序列化的示例。</span><span class="sxs-lookup"><span data-stu-id="9e3a1-103">This topic shows an example that serializes and deserializes using <xref:System.Xml.Serialization.XmlSerializer>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9e3a1-104">示例</span><span class="sxs-lookup"><span data-stu-id="9e3a1-104">Example</span></span>  
 <span data-ttu-id="9e3a1-105">下面的示例创建多个包含 <xref:System.Xml.Linq.XElement> 对象的对象。</span><span class="sxs-lookup"><span data-stu-id="9e3a1-105">The following example creates a number of objects that contain <xref:System.Xml.Linq.XElement> objects.</span></span> <span data-ttu-id="9e3a1-106">然后将它们序列化为内存流，接着从内存流对它们进行反序列化。</span><span class="sxs-lookup"><span data-stu-id="9e3a1-106">It then serializes them to a memory stream, and then deserializes them from the memory stream.</span></span>  
  
```vb  
Imports System  
Imports System.Xml  
Imports System.Xml.Linq  
Imports System.IO  
Imports System.Runtime.Serialization  
Imports System.Xml.Serialization  
  
Public Class XElementContainer  
    Public member As XElement  
  
    Public Sub XElementContainer()  
        member = XLinqTest.CreateXElement()  
    End Sub  
  
    Overrides Function ToString() As String  
        Return member.ToString()  
    End Function  
End Class  
  
Public Class XElementNullContainer  
    Public member As XElement  
  
    Public Sub XElementNullContainer()  
        member = Nothing  
    End Sub  
End Class  
  
Public Class XLinqTest  
    Shared Sub Main()  
        Test(Of XElementNullContainer)(New XElementNullContainer())  
        Test(Of XElement)(CreateXElement())  
        Test(Of XElementContainer)(New XElementContainer())  
    End Sub  
  
    Public Shared Function CreateXElement() As XElement  
        Dim ns As XNamespace = "http://www.adventure-works.com"  
        Return New XElement(ns + "aw")  
    End Function  
  
    Public Shared Sub Test(Of T)(ByRef obj)  
        Using stream As New MemoryStream()  
            Dim s As XmlSerializer = New XmlSerializer(GetType(T))  
            Console.WriteLine("Testing for type: {0}", GetType(T))  
            s.Serialize(XmlWriter.Create(stream), obj)  
            stream.Flush()  
            stream.Seek(0, SeekOrigin.Begin)  
            Dim o As Object = s.Deserialize(XmlReader.Create(stream))  
            Console.WriteLine("  Deserialized type: {0}", o.GetType())  
        End Using  
    End Sub  
End Class  
```  
  
 <span data-ttu-id="9e3a1-107">该示例产生下面的输出：</span><span class="sxs-lookup"><span data-stu-id="9e3a1-107">This example produces the following output:</span></span>  
  
```  
Testing for type: XElementNullContainer  
  Deserialized type: XElementNullContainer  
Testing for type: System.Xml.Linq.XElement  
  Deserialized type: System.Xml.Linq.XElement  
Testing for type: XElementContainer  
  Deserialized type: XElementContainer  
```  
  
## <a name="see-also"></a><span data-ttu-id="9e3a1-108">请参阅</span><span class="sxs-lookup"><span data-stu-id="9e3a1-108">See also</span></span>

- [<span data-ttu-id="9e3a1-109">序列化包含 XElement 对象 (Visual Basic 中) 的对象图</span><span class="sxs-lookup"><span data-stu-id="9e3a1-109">Serializing Object Graphs that Contain XElement Objects (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/serializing-object-graphs-that-contain-xelement-objects.md)
