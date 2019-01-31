---
title: 如何：将对象数据写入 XML 文件 (C#)
ms.date: 07/20/2015
ms.assetid: 7681eb98-703d-4005-a369-26a7bca0f894
ms.openlocfilehash: 064d7ed61921f3f700311a1b09ee77e0c9818d71
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54554278"
---
# <a name="how-to-write-object-data-to-an-xml-file-c"></a><span data-ttu-id="d7b25-102">如何：将对象数据写入 XML 文件 (C#)</span><span class="sxs-lookup"><span data-stu-id="d7b25-102">How to: Write Object Data to an XML File (C#)</span></span>
<span data-ttu-id="d7b25-103">本示例使用 <xref:System.Xml.Serialization.XmlSerializer> 类从某个类将对象写入 XML 文件。</span><span class="sxs-lookup"><span data-stu-id="d7b25-103">This example writes the object from a class to an XML file using the <xref:System.Xml.Serialization.XmlSerializer> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d7b25-104">示例</span><span class="sxs-lookup"><span data-stu-id="d7b25-104">Example</span></span>  
  
```csharp  
public class XMLWrite  
{  
  
   static void Main(string[] args)  
    {  
        WriteXML();  
    }  
  
    public class Book  
    {  
        public String title;   
    }  
  
    public static void WriteXML()  
    {  
        Book overview = new Book();  
        overview.title = "Serialization Overview";  
        System.Xml.Serialization.XmlSerializer writer =   
            new System.Xml.Serialization.XmlSerializer(typeof(Book));  
  
        var path = Environment.GetFolderPath(Environment.SpecialFolder.MyDocuments) + "//SerializationOverview.xml";  
        System.IO.FileStream file = System.IO.File.Create(path);  
  
        writer.Serialize(file, overview);  
        file.Close();  
    }  
}  
```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="d7b25-105">编译代码</span><span class="sxs-lookup"><span data-stu-id="d7b25-105">Compiling the Code</span></span>  
 <span data-ttu-id="d7b25-106">类必须有一个公共的无参数构造函数。</span><span class="sxs-lookup"><span data-stu-id="d7b25-106">The class must have a public constructor without parameters.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="d7b25-107">可靠编程</span><span class="sxs-lookup"><span data-stu-id="d7b25-107">Robust Programming</span></span>  
 <span data-ttu-id="d7b25-108">以下情况可能会导致异常：</span><span class="sxs-lookup"><span data-stu-id="d7b25-108">The following conditions may cause an exception:</span></span>  
  
-   <span data-ttu-id="d7b25-109">进行序列化的类没有公共的无参数构造函数。</span><span class="sxs-lookup"><span data-stu-id="d7b25-109">The class being serialized does not have a public, parameterless constructor.</span></span>  
  
-   <span data-ttu-id="d7b25-110">文件存在且为只读 (<xref:System.IO.IOException>)。</span><span class="sxs-lookup"><span data-stu-id="d7b25-110">The file exists and is read-only (<xref:System.IO.IOException>).</span></span>  
  
-   <span data-ttu-id="d7b25-111">路径过长 (<xref:System.IO.PathTooLongException>)。</span><span class="sxs-lookup"><span data-stu-id="d7b25-111">The path is too long (<xref:System.IO.PathTooLongException>).</span></span>  
  
-   <span data-ttu-id="d7b25-112">磁盘已满 (<xref:System.IO.IOException>)。</span><span class="sxs-lookup"><span data-stu-id="d7b25-112">The disk is full (<xref:System.IO.IOException>).</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="d7b25-113">.NET Framework 安全性</span><span class="sxs-lookup"><span data-stu-id="d7b25-113">.NET Framework Security</span></span>  
 <span data-ttu-id="d7b25-114">此示例在文件尚未存在时创建新文件。</span><span class="sxs-lookup"><span data-stu-id="d7b25-114">This example creates a new file, if the file does not already exist.</span></span> <span data-ttu-id="d7b25-115">如果某个应用程序需要创建文件，则该应用程序需要针对文件夹的 `Create` 访问权限。</span><span class="sxs-lookup"><span data-stu-id="d7b25-115">If an application needs to create a file, that application needs `Create` access for the folder.</span></span> <span data-ttu-id="d7b25-116">如果文件已存在，则该应用程序只需要 `Write` 访问权限（这是较弱的特权）。</span><span class="sxs-lookup"><span data-stu-id="d7b25-116">If the file already exists, the application needs only `Write` access, a lesser privilege.</span></span> <span data-ttu-id="d7b25-117">如有可能，在部署过程中创建文件，并且仅授予针对单个文件的 `Read` 访问权限（而不是针对 `Create` 文件夹的访问权限）会更加安全。</span><span class="sxs-lookup"><span data-stu-id="d7b25-117">Where possible, it is more secure to create the file during deployment, and only grant `Read` access to a single file, rather than `Create` access for a folder.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d7b25-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="d7b25-118">See also</span></span>

- <xref:System.IO.StreamWriter>
- [<span data-ttu-id="d7b25-119">如何：从 XML 文件读取对象数据 (C#)</span><span class="sxs-lookup"><span data-stu-id="d7b25-119">How to: Read Object Data from an XML File (C#)</span></span>](../../../../csharp/programming-guide/concepts/serialization/how-to-read-object-data-from-an-xml-file.md)
- [<span data-ttu-id="d7b25-120">序列化 (C#)</span><span class="sxs-lookup"><span data-stu-id="d7b25-120">Serialization (C#)</span></span>](../../../../csharp/programming-guide/concepts/serialization/index.md)
