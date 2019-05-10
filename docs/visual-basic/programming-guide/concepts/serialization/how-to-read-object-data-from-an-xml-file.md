---
title: 如何：从 XML 文件 (Visual Basic 中) 中读取对象数据
ms.date: 07/20/2015
ms.assetid: 1e1423bf-74a4-4dde-a3bb-ae1bfc0a68ed
ms.openlocfilehash: b1e9033d7aba8b4f423f29cd4fb4f7efbbe17a29
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "64624363"
---
# <a name="how-to-read-object-data-from-an-xml-file-visual-basic"></a><span data-ttu-id="683f0-102">如何：从 XML 文件 (Visual Basic 中) 中读取对象数据</span><span class="sxs-lookup"><span data-stu-id="683f0-102">How to: Read Object Data from an XML File (Visual Basic)</span></span>
<span data-ttu-id="683f0-103">本示例使用 <xref:System.Xml.Serialization.XmlSerializer> 类读取之前写入 XML 文件的对象数据。</span><span class="sxs-lookup"><span data-stu-id="683f0-103">This example reads object data that was previously written to an XML file using the <xref:System.Xml.Serialization.XmlSerializer> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="683f0-104">示例</span><span class="sxs-lookup"><span data-stu-id="683f0-104">Example</span></span>  
  
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
  
## <a name="compiling-the-code"></a><span data-ttu-id="683f0-105">编译代码</span><span class="sxs-lookup"><span data-stu-id="683f0-105">Compiling the Code</span></span>  
 <span data-ttu-id="683f0-106">将文件名称“c:\temp\SerializationOverview.xml”替换为包含序列化数据的文件的名称。</span><span class="sxs-lookup"><span data-stu-id="683f0-106">Replace the file name "c:\temp\SerializationOverview.xml" with the name of the file containing the serialized data.</span></span> <span data-ttu-id="683f0-107">有关如何序列化数据的详细信息，请参阅[如何：将对象数据写入到 XML 文件 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/serialization/how-to-write-object-data-to-an-xml-file.md)。</span><span class="sxs-lookup"><span data-stu-id="683f0-107">For more information about serializing data, see [How to: Write Object Data to an XML File (Visual Basic)](../../../../visual-basic/programming-guide/concepts/serialization/how-to-write-object-data-to-an-xml-file.md).</span></span>  
  
 <span data-ttu-id="683f0-108">类必须有一个公共的无参数构造函数。</span><span class="sxs-lookup"><span data-stu-id="683f0-108">The class must have a public constructor without parameters.</span></span>  
  
 <span data-ttu-id="683f0-109">只有公共属性和字段才会进行反序列化。</span><span class="sxs-lookup"><span data-stu-id="683f0-109">Only public properties and fields are deserialized.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="683f0-110">可靠编程</span><span class="sxs-lookup"><span data-stu-id="683f0-110">Robust Programming</span></span>  
 <span data-ttu-id="683f0-111">以下情况可能会导致异常：</span><span class="sxs-lookup"><span data-stu-id="683f0-111">The following conditions may cause an exception:</span></span>  
  
- <span data-ttu-id="683f0-112">进行序列化的类没有公共的无参数构造函数。</span><span class="sxs-lookup"><span data-stu-id="683f0-112">The class being serialized does not have a public, parameterless constructor.</span></span>  
  
- <span data-ttu-id="683f0-113">文件中的数据不表示要进行反序列化的类中的数据。</span><span class="sxs-lookup"><span data-stu-id="683f0-113">The data in the file does not represent data from the class to be deserialized.</span></span>  
  
- <span data-ttu-id="683f0-114">该文件不存在 (<xref:System.IO.IOException>)。</span><span class="sxs-lookup"><span data-stu-id="683f0-114">The file does not exist (<xref:System.IO.IOException>).</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="683f0-115">.NET Framework 安全性</span><span class="sxs-lookup"><span data-stu-id="683f0-115">.NET Framework Security</span></span>  
 <span data-ttu-id="683f0-116">始终验证输入，并且绝不会反序列化来自不受信任源的数据。</span><span class="sxs-lookup"><span data-stu-id="683f0-116">Always verify inputs, and never deserialize data from an untrusted source.</span></span> <span data-ttu-id="683f0-117">重新创建的对象会在具有对它进行反序列化的代码的权限的本地计算机上运行。</span><span class="sxs-lookup"><span data-stu-id="683f0-117">The re-created object runs on a local computer with the permissions of the code that deserialized it.</span></span> <span data-ttu-id="683f0-118">在应用程序中使用输入的数据之前，需验证所有的输入内容。</span><span class="sxs-lookup"><span data-stu-id="683f0-118">Verify all inputs before using the data in your application.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="683f0-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="683f0-119">See also</span></span>

- <xref:System.IO.StreamWriter>
- [<span data-ttu-id="683f0-120">如何：将对象数据写入到 XML 文件 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="683f0-120">How to: Write Object Data to an XML File (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/serialization/how-to-write-object-data-to-an-xml-file.md)
- [<span data-ttu-id="683f0-121">序列化 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="683f0-121">Serialization (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/serialization/index.md)
- [<span data-ttu-id="683f0-122">Visual Basic 编程指南</span><span class="sxs-lookup"><span data-stu-id="683f0-122">Visual Basic Programming Guide</span></span>](../../../../visual-basic/programming-guide/index.md)
