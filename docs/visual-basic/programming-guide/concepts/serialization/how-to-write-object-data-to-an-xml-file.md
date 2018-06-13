---
title: 如何： 将对象数据写入到 XML 文件 (Visual Basic)
ms.date: 07/20/2015
ms.assetid: f7966480-5ed2-43ac-9894-33427436de2a
ms.openlocfilehash: 434706383c50e5df8e419e3988da8dc7cce87c83
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33652544"
---
# <a name="how-to-write-object-data-to-an-xml-file-visual-basic"></a><span data-ttu-id="d0764-102">如何： 将对象数据写入到 XML 文件 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d0764-102">How to: Write Object Data to an XML File (Visual Basic)</span></span>
<span data-ttu-id="d0764-103">本示例使用 <xref:System.Xml.Serialization.XmlSerializer> 类从某个类将对象写入 XML 文件。</span><span class="sxs-lookup"><span data-stu-id="d0764-103">This example writes the object from a class to an XML file using the <xref:System.Xml.Serialization.XmlSerializer> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d0764-104">示例</span><span class="sxs-lookup"><span data-stu-id="d0764-104">Example</span></span>  
  
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
  
## <a name="compiling-the-code"></a><span data-ttu-id="d0764-105">编译代码</span><span class="sxs-lookup"><span data-stu-id="d0764-105">Compiling the Code</span></span>  
 <span data-ttu-id="d0764-106">类必须有一个公共的无参数构造函数。</span><span class="sxs-lookup"><span data-stu-id="d0764-106">The class must have a public constructor without parameters.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="d0764-107">可靠编程</span><span class="sxs-lookup"><span data-stu-id="d0764-107">Robust Programming</span></span>  
 <span data-ttu-id="d0764-108">以下情况可能会导致异常：</span><span class="sxs-lookup"><span data-stu-id="d0764-108">The following conditions may cause an exception:</span></span>  
  
-   <span data-ttu-id="d0764-109">进行序列化的类没有公共的无参数构造函数。</span><span class="sxs-lookup"><span data-stu-id="d0764-109">The class being serialized does not have a public, parameterless constructor.</span></span>  
  
-   <span data-ttu-id="d0764-110">文件存在且为只读 (<xref:System.IO.IOException>)。</span><span class="sxs-lookup"><span data-stu-id="d0764-110">The file exists and is read-only (<xref:System.IO.IOException>).</span></span>  
  
-   <span data-ttu-id="d0764-111">路径过长 (<xref:System.IO.PathTooLongException>)。</span><span class="sxs-lookup"><span data-stu-id="d0764-111">The path is too long (<xref:System.IO.PathTooLongException>).</span></span>  
  
-   <span data-ttu-id="d0764-112">磁盘已满 (<xref:System.IO.IOException>)。</span><span class="sxs-lookup"><span data-stu-id="d0764-112">The disk is full (<xref:System.IO.IOException>).</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="d0764-113">.NET Framework 安全性</span><span class="sxs-lookup"><span data-stu-id="d0764-113">.NET Framework Security</span></span>  
 <span data-ttu-id="d0764-114">此示例在文件尚未存在时创建新文件。</span><span class="sxs-lookup"><span data-stu-id="d0764-114">This example creates a new file, if the file does not already exist.</span></span> <span data-ttu-id="d0764-115">如果某个应用程序需要创建文件，则该应用程序需要针对文件夹的 `Create` 访问权限。</span><span class="sxs-lookup"><span data-stu-id="d0764-115">If an application needs to create a file, that application needs `Create` access for the folder.</span></span> <span data-ttu-id="d0764-116">如果文件已存在，则该应用程序只需要 `Write` 访问权限（这是较弱的特权）。</span><span class="sxs-lookup"><span data-stu-id="d0764-116">If the file already exists, the application needs only `Write` access, a lesser privilege.</span></span> <span data-ttu-id="d0764-117">如有可能，在部署过程中创建文件，并且仅授予针对单个文件的 `Read` 访问权限（而不是针对 `Create` 文件夹的访问权限）会更加安全。</span><span class="sxs-lookup"><span data-stu-id="d0764-117">Where possible, it is more secure to create the file during deployment, and only grant `Read` access to a single file, rather than `Create` access for a folder.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d0764-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="d0764-118">See Also</span></span>  
 <xref:System.IO.StreamWriter>  
 [<span data-ttu-id="d0764-119">如何：读取 XML 文件中的对象数据 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d0764-119">How to: Read Object Data from an XML File (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/serialization/how-to-read-object-data-from-an-xml-file.md)  
 [<span data-ttu-id="d0764-120">序列化 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d0764-120">Serialization (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/serialization/index.md)
