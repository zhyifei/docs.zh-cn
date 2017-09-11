---
title: "如何︰ 将对象数据写入到 XML 文件 (Visual Basic 中) |Microsoft 文档"
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
ms.assetid: f7966480-5ed2-43ac-9894-33427436de2a
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
ms.openlocfilehash: 27131f357c1f5afc75645bff88ae5d7cd2395617
ms.contentlocale: zh-cn
ms.lasthandoff: 04/12/2017

---
# <a name="how-to-write-object-data-to-an-xml-file-visual-basic"></a><span data-ttu-id="cdfba-102">如何︰ 将对象数据写入到 XML 文件 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="cdfba-102">How to: Write Object Data to an XML File (Visual Basic)</span></span>
<span data-ttu-id="cdfba-103">该示例将对象从类写入到 XML 文件使用<xref:System.Xml.Serialization.XmlSerializer>类。</xref:System.Xml.Serialization.XmlSerializer></span><span class="sxs-lookup"><span data-stu-id="cdfba-103">TThis example writes the object from a class to an XML file using the <xref:System.Xml.Serialization.XmlSerializer> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="cdfba-104">示例</span><span class="sxs-lookup"><span data-stu-id="cdfba-104">Example</span></span>  
  
```vb  
Public Module XMLWrite  
  
    Sub Main()  
        WriteXML()  
    End Sub  
  
    Public Class Book  
        Public Title As String  
    End Class  
  
    Public Sub WriteXML()  
        Dim overview As New Book  
        overview.Title = "Serialization Overview"  
        Dim writer As New System.Xml.Serialization.XmlSerializer(GetType(Book))  
        Dim file As New System.IO.StreamWriter(  
            "c:\temp\SerializationOverview.xml")  
        writer.Serialize(file, overview)  
        file.Close()  
    End Sub  
End Module  
```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="cdfba-105">编译代码</span><span class="sxs-lookup"><span data-stu-id="cdfba-105">Compiling the Code</span></span>  
 <span data-ttu-id="cdfba-106">此类必须具有不带参数的公共构造函数。</span><span class="sxs-lookup"><span data-stu-id="cdfba-106">The class must have a public constructor without parameters.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="cdfba-107">可靠编程</span><span class="sxs-lookup"><span data-stu-id="cdfba-107">Robust Programming</span></span>  
 <span data-ttu-id="cdfba-108">以下情况可能会导致异常：</span><span class="sxs-lookup"><span data-stu-id="cdfba-108">The following conditions may cause an exception:</span></span>  
  
-   <span data-ttu-id="cdfba-109">正在序列化的类没有公共的无参数构造函数。</span><span class="sxs-lookup"><span data-stu-id="cdfba-109">The class being serialized does not have a public, parameterless constructor.</span></span>  
  
-   <span data-ttu-id="cdfba-110">文件存在并且是只读的 (<xref:System.IO.IOException>)。</xref:System.IO.IOException></span><span class="sxs-lookup"><span data-stu-id="cdfba-110">The file exists and is read-only (<xref:System.IO.IOException>).</span></span>  
  
-   <span data-ttu-id="cdfba-111">路径过长 (<xref:System.IO.PathTooLongException>)。</xref:System.IO.PathTooLongException></span><span class="sxs-lookup"><span data-stu-id="cdfba-111">The path is too long (<xref:System.IO.PathTooLongException>).</span></span>  
  
-   <span data-ttu-id="cdfba-112">磁盘已满 (<xref:System.IO.IOException>)。</xref:System.IO.IOException></span><span class="sxs-lookup"><span data-stu-id="cdfba-112">The disk is full (<xref:System.IO.IOException>).</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="cdfba-113">.NET Framework 安全性</span><span class="sxs-lookup"><span data-stu-id="cdfba-113">.NET Framework Security</span></span>  
 <span data-ttu-id="cdfba-114">此示例创建一个新文件，如果该文件不存在。</span><span class="sxs-lookup"><span data-stu-id="cdfba-114">This example creates a new file, if the file does not already exist.</span></span> <span data-ttu-id="cdfba-115">如果应用程序需要创建一个文件，该应用程序需要`Create`文件夹的访问。</span><span class="sxs-lookup"><span data-stu-id="cdfba-115">If an application needs to create a file, that application needs `Create` access for the folder.</span></span> <span data-ttu-id="cdfba-116">如果该文件已存在，该应用程序仅需要`Write`访问，较弱的特权。</span><span class="sxs-lookup"><span data-stu-id="cdfba-116">If the file already exists, the application needs only `Write` access, a lesser privilege.</span></span> <span data-ttu-id="cdfba-117">如有可能，会在部署期间，创建该文件，并仅授予更安全`Read`访问单个文件，而不是`Create`文件夹的访问。</span><span class="sxs-lookup"><span data-stu-id="cdfba-117">Where possible, it is more secure to create the file during deployment, and only grant `Read` access to a single file, rather than `Create` access for a folder.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cdfba-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="cdfba-118">See Also</span></span>  
 <span data-ttu-id="cdfba-119"><xref:System.IO.StreamWriter></xref:System.IO.StreamWriter></span><span class="sxs-lookup"><span data-stu-id="cdfba-119"><xref:System.IO.StreamWriter></span></span>   
<span data-ttu-id="cdfba-120"> [如何︰ 从 XML 文件 (Visual Basic 中) 中读取对象数据](../../../../visual-basic/programming-guide/concepts/serialization/how-to-read-object-data-from-an-xml-file.md) </span><span class="sxs-lookup"><span data-stu-id="cdfba-120"> [How to: Read Object Data from an XML File (Visual Basic)](../../../../visual-basic/programming-guide/concepts/serialization/how-to-read-object-data-from-an-xml-file.md) </span></span>  
<span data-ttu-id="cdfba-121"> [序列化 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/serialization/index.md)</span><span class="sxs-lookup"><span data-stu-id="cdfba-121"> [Serialization (Visual Basic)](../../../../visual-basic/programming-guide/concepts/serialization/index.md)</span></span>
