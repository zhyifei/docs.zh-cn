---
title: "如何︰ 从 XML 文件 (Visual Basic 中) 中读取对象数据 |Microsoft 文档"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
ms.assetid: 1e1423bf-74a4-4dde-a3bb-ae1bfc0a68ed
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 3b9697f763a2d781c37960d46cbc7fa4536c84b4
ms.contentlocale: zh-cn
ms.lasthandoff: 04/12/2017

---
# <a name="how-to-read-object-data-from-an-xml-file-visual-basic"></a><span data-ttu-id="0e629-102">如何︰ 从 XML 文件 (Visual Basic 中) 中读取对象数据</span><span class="sxs-lookup"><span data-stu-id="0e629-102">How to: Read Object Data from an XML File (Visual Basic)</span></span>
<span data-ttu-id="0e629-103">以下示例将读取对象数据时，以前写入 XML 文件中使用<xref:System.Xml.Serialization.XmlSerializer>类。</xref:System.Xml.Serialization.XmlSerializer></span><span class="sxs-lookup"><span data-stu-id="0e629-103">This example reads object data that was previously written to an XML file using the <xref:System.Xml.Serialization.XmlSerializer> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0e629-104">示例</span><span class="sxs-lookup"><span data-stu-id="0e629-104">Example</span></span>  
  
```vb  
Public Class Book  
    Public Title As String  
End Class  
  
Public Sub ReadXML()  
    Dim reader As New System.Xml.Serialization.XmlSerializer(GetType(Book))  
    Dim file As New System.IO.StreamReader(  
        "c:\temp\SerializationOverview.xml")  
    Dim overview As Book  
    overview = CType(reader.Deserialize(file), Book)  
    Console.WriteLine(overview.Title)  
End Sub  
```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="0e629-105">编译代码</span><span class="sxs-lookup"><span data-stu-id="0e629-105">Compiling the Code</span></span>  
 <span data-ttu-id="0e629-106">文件名称"c:\temp\SerializationOverview.xml"替换为包含序列化的数据的文件的名称。</span><span class="sxs-lookup"><span data-stu-id="0e629-106">Replace the file name "c:\temp\SerializationOverview.xml" with the name of the file containing the serialized data.</span></span> <span data-ttu-id="0e629-107">有关序列化数据的详细信息，请参阅[如何︰ 将对象数据写入到 XML 文件 (Visual Basic 中)](../../../../visual-basic/programming-guide/concepts/serialization/how-to-write-object-data-to-an-xml-file.md)。</span><span class="sxs-lookup"><span data-stu-id="0e629-107">For more information about serializing data, see [How to: Write Object Data to an XML File (Visual Basic)](../../../../visual-basic/programming-guide/concepts/serialization/how-to-write-object-data-to-an-xml-file.md).</span></span>  
  
 <span data-ttu-id="0e629-108">此类必须具有不带参数的公共构造函数。</span><span class="sxs-lookup"><span data-stu-id="0e629-108">The class must have a public constructor without parameters.</span></span>  
  
 <span data-ttu-id="0e629-109">只有公共属性和字段被反序列化。</span><span class="sxs-lookup"><span data-stu-id="0e629-109">Only public properties and fields are deserialized.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="0e629-110">可靠编程</span><span class="sxs-lookup"><span data-stu-id="0e629-110">Robust Programming</span></span>  
 <span data-ttu-id="0e629-111">以下情况可能会导致异常：</span><span class="sxs-lookup"><span data-stu-id="0e629-111">The following conditions may cause an exception:</span></span>  
  
-   <span data-ttu-id="0e629-112">正在序列化的类没有公共的无参数构造函数。</span><span class="sxs-lookup"><span data-stu-id="0e629-112">The class being serialized does not have a public, parameterless constructor.</span></span>  
  
-   <span data-ttu-id="0e629-113">文件中的数据不表示从类要反序列化的数据。</span><span class="sxs-lookup"><span data-stu-id="0e629-113">The data in the file does not represent data from the class to be deserialized.</span></span>  
  
-   <span data-ttu-id="0e629-114">该文件不存在 (<xref:System.IO.IOException>)。</xref:System.IO.IOException></span><span class="sxs-lookup"><span data-stu-id="0e629-114">The file does not exist (<xref:System.IO.IOException>).</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="0e629-115">.NET Framework 安全性</span><span class="sxs-lookup"><span data-stu-id="0e629-115">.NET Framework Security</span></span>  
 <span data-ttu-id="0e629-116">始终验证输入内容，并且永远不会反序列化来自不受信任源的数据。</span><span class="sxs-lookup"><span data-stu-id="0e629-116">Always verify inputs, and never deserialize data from an untrusted source.</span></span> <span data-ttu-id="0e629-117">重新创建的对象在反序列化其代码的权限的本地计算机上运行。</span><span class="sxs-lookup"><span data-stu-id="0e629-117">The re-created object runs on a local computer with the permissions of the code that deserialized it.</span></span> <span data-ttu-id="0e629-118">在应用程序中使用输入的数据之前，需验证所有的输入内容。</span><span class="sxs-lookup"><span data-stu-id="0e629-118">Verify all inputs before using the data in your application.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0e629-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0e629-119">See Also</span></span>  
 <span data-ttu-id="0e629-120"><xref:System.IO.StreamWriter></xref:System.IO.StreamWriter></span><span class="sxs-lookup"><span data-stu-id="0e629-120"><xref:System.IO.StreamWriter></span></span>   
<span data-ttu-id="0e629-121"> [如何︰ 将对象数据写入到 XML 文件 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/serialization/how-to-write-object-data-to-an-xml-file.md) </span><span class="sxs-lookup"><span data-stu-id="0e629-121"> [How to: Write Object Data to an XML File (Visual Basic)](../../../../visual-basic/programming-guide/concepts/serialization/how-to-write-object-data-to-an-xml-file.md) </span></span>  
<span data-ttu-id="0e629-122"> [序列化 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/serialization/index.md) </span><span class="sxs-lookup"><span data-stu-id="0e629-122"> [Serialization (Visual Basic)](../../../../visual-basic/programming-guide/concepts/serialization/index.md) </span></span>  
<span data-ttu-id="0e629-123"> [Visual Basic 编程指南](../../../../visual-basic/programming-guide/index.md)</span><span class="sxs-lookup"><span data-stu-id="0e629-123"> [Visual Basic Programming Guide](../../../../visual-basic/programming-guide/index.md)</span></span>
