---
title: "如何：使用 DataContractSerializer 进行序列化 (C#)"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
ms.assetid: 3320ecbf-cdbe-480e-979c-2c14bbef9988
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: da57267bb8fd33263c950db0ca3d0a5b1b5817d4
ms.contentlocale: zh-cn
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-serialize-using-datacontractserializer-c"></a><span data-ttu-id="80ac6-102">如何：使用 DataContractSerializer 进行序列化 (C#)</span><span class="sxs-lookup"><span data-stu-id="80ac6-102">How to: Serialize Using DataContractSerializer (C#)</span></span>
<span data-ttu-id="80ac6-103">本主题显示一个使用 <xref:System.Runtime.Serialization.DataContractSerializer> 进行序列化和反序列化的示例。</span><span class="sxs-lookup"><span data-stu-id="80ac6-103">This topic shows an example that serializes and deserializes using <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="80ac6-104">示例</span><span class="sxs-lookup"><span data-stu-id="80ac6-104">Example</span></span>  
 <span data-ttu-id="80ac6-105">下面的示例创建多个包含 <xref:System.Xml.Linq.XElement> 对象的对象。</span><span class="sxs-lookup"><span data-stu-id="80ac6-105">The following example creates a number of objects that contain <xref:System.Xml.Linq.XElement> objects.</span></span> <span data-ttu-id="80ac6-106">然后将它们序列化为文本文件，接着从文本文件对它们进行反序列化。</span><span class="sxs-lookup"><span data-stu-id="80ac6-106">It then serializes them to text files, and then deserializes them from the text files.</span></span>  
  
```csharp  
using System;  
using System.Xml;  
using System.Xml.Linq;  
using System.IO;  
using System.Runtime.Serialization;  
  
public class XLinqTest  
{  
    public static void Main()  
    {  
        Test<XElement>(CreateXElement());  
        Test<XElementContainer>(new XElementContainer());  
        Test<XElementNullContainer>(new XElementNullContainer());  
    }  
  
    public static void Test<T>(T obj)  
    {  
        DataContractSerializer s = new DataContractSerializer(typeof(T));  
        using (FileStream fs = File.Open("test" + typeof(T).Name + ".xml", FileMode.Create))  
        {  
            Console.WriteLine("Testing for type: {0}", typeof(T));   
            s.WriteObject(fs, obj);  
        }  
        using (FileStream fs = File.Open("test" + typeof(T).Name + ".xml", FileMode.Open))  
        {  
            object s2 = s.ReadObject(fs);  
            if (s2 == null)  
                Console.WriteLine("  Deserialized object is null (Nothing in VB)");  
            else  
                Console.WriteLine("  Deserialized type: {0}", s2.GetType());  
        }  
    }  
  
    public static XElement CreateXElement()  
    {  
        return new XElement(XName.Get("NameInNamespace", "http://www.adventure-works.org"));  
    }  
}  
  
[DataContract]  
public class XElementContainer  
{  
    [DataMember]  
    public XElement member;  
  
    public XElementContainer()  
    {  
        member = XLinqTest.CreateXElement();  
    }  
}  
  
[DataContract]  
public class XElementNullContainer  
{  
    [DataMember]  
    public XElement member;  
  
    public XElementNullContainer()  
    {  
        member = null;  
    }  
}  
```  
  
 <span data-ttu-id="80ac6-107">该示例产生下面的输出：</span><span class="sxs-lookup"><span data-stu-id="80ac6-107">This example produces the following output:</span></span>  
  
```  
Testing for type: System.Xml.Linq.XElement  
  Deserialized type: System.Xml.Linq.XElement  
Testing for type: XElementContainer  
  Deserialized type: XElementContainer  
Testing for type: XElementNullContainer  
  Deserialized type: XElementNullContainer  
```  
  
## <a name="see-also"></a><span data-ttu-id="80ac6-108">请参阅</span><span class="sxs-lookup"><span data-stu-id="80ac6-108">See Also</span></span>  
 [<span data-ttu-id="80ac6-109">序列化包含 XElement 对象的对象图 (C#)</span><span class="sxs-lookup"><span data-stu-id="80ac6-109">Serializing Object Graphs that Contain XElement Objects (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/serializing-object-graphs-that-contain-xelement-objects.md)

