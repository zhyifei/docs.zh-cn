---
title: "XML 数据类型的转换"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: a2aa99ba-8239-4818-9281-f1d72ee40bde
caps.latest.revision: "3"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: d2f5f5d27b3d21ff12f5eea7613e80e73c5b6597
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="conversion-of-xml-data-types"></a><span data-ttu-id="43101-102">XML 数据类型的转换</span><span class="sxs-lookup"><span data-stu-id="43101-102">Conversion of XML Data Types</span></span>
<span data-ttu-id="43101-103">中的多数方法找到**XmlConvert**类用于将转换字符串和强类型化格式之间的数据。</span><span class="sxs-lookup"><span data-stu-id="43101-103">The majority of the methods found in an **XmlConvert** class are used to convert data between strings and strongly-typed formats.</span></span> <span data-ttu-id="43101-104">这些方法与区域设置无关。</span><span class="sxs-lookup"><span data-stu-id="43101-104">Methods are locale independent.</span></span> <span data-ttu-id="43101-105">这意味着它们在执行转换时不考虑任何区域设置。</span><span class="sxs-lookup"><span data-stu-id="43101-105">This means that they do not take into account any locale settings when doing conversion.</span></span>  
  
## <a name="reading-string-as-types"></a><span data-ttu-id="43101-106">将字符串作为类型读取</span><span class="sxs-lookup"><span data-stu-id="43101-106">Reading String as types</span></span>  
 <span data-ttu-id="43101-107">下面的示例读取一个字符串，并将其转换为**DateTime**类型。</span><span class="sxs-lookup"><span data-stu-id="43101-107">The following sample reads a string and converts it to a **DateTime** type.</span></span>  
  
 <span data-ttu-id="43101-108">给定以下 XML 输入：</span><span class="sxs-lookup"><span data-stu-id="43101-108">Given the following XML input:</span></span>  
  
 <span data-ttu-id="43101-109">**输入**</span><span class="sxs-lookup"><span data-stu-id="43101-109">**Input**</span></span>  
  
```xml  
<Element>2001-02-27T11:13:23</Element>  
```  
  
 <span data-ttu-id="43101-110">此代码将字符串转换为**DateTime**格式：</span><span class="sxs-lookup"><span data-stu-id="43101-110">This code converts the string to the **DateTime** format:</span></span>  
  
```vb  
reader.ReadStartElement()  
Dim vDateTime As DateTime = XmlConvert.ToDateTime(reader.ReadString())  
Console.WriteLine(vDateTime)  
```  
  
```csharp  
reader.ReadStartElement();  
DateTime vDateTime = XmlConvert.ToDateTime(reader.ReadString());  
Console.WriteLine(vDateTime);  
```  
  
## <a name="writing-strings-as-types"></a><span data-ttu-id="43101-111">将字符串作为类型写入</span><span class="sxs-lookup"><span data-stu-id="43101-111">Writing Strings as types</span></span>  
 <span data-ttu-id="43101-112">下面的示例读取**Int32**并将其转换为字符串。</span><span class="sxs-lookup"><span data-stu-id="43101-112">The following sample reads an **Int32** and converts it to a string.</span></span>  
  
 <span data-ttu-id="43101-113">给定以下 XML 输入：</span><span class="sxs-lookup"><span data-stu-id="43101-113">Given the following XML input:</span></span>  
  
 <span data-ttu-id="43101-114">**输入**</span><span class="sxs-lookup"><span data-stu-id="43101-114">**Input**</span></span>  
  
```xml  
<TestInt32>-2147483648</TestInt32>  
```  
  
 <span data-ttu-id="43101-115">下面的代码将**Int32**到**字符串**:</span><span class="sxs-lookup"><span data-stu-id="43101-115">This code converts the **Int32** into a **String**:</span></span>  
  
```vb  
Dim vInt32 As Int32 = -2147483648  
writer.WriteElementString("TestInt32", XmlConvert.ToString(vInt32))  
```  
  
```csharp  
Int32 vInt32=-2147483648;  
writer.WriteElementString("TestInt32",XmlConvert.ToString(vInt32));  
```  
  
## <a name="see-also"></a><span data-ttu-id="43101-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="43101-116">See Also</span></span>  
 [<span data-ttu-id="43101-117">将字符串转换为.NET Framework 数据类型</span><span class="sxs-lookup"><span data-stu-id="43101-117">Converting Strings to .NET Framework Data Types</span></span>](../../../../docs/standard/data/xml/converting-strings-to-dotnet-data-types.md)  
 [<span data-ttu-id="43101-118">将.NET Framework 类型转换为字符串</span><span class="sxs-lookup"><span data-stu-id="43101-118">Converting .NET Framework Types to Strings</span></span>](../../../../docs/standard/data/xml/converting-dotnet-types-to-strings.md)
