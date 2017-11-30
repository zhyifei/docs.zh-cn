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
# <a name="conversion-of-xml-data-types"></a>XML 数据类型的转换
中的多数方法找到**XmlConvert**类用于将转换字符串和强类型化格式之间的数据。 这些方法与区域设置无关。 这意味着它们在执行转换时不考虑任何区域设置。  
  
## <a name="reading-string-as-types"></a>将字符串作为类型读取  
 下面的示例读取一个字符串，并将其转换为**DateTime**类型。  
  
 给定以下 XML 输入：  
  
 **输入**  
  
```xml  
<Element>2001-02-27T11:13:23</Element>  
```  
  
 此代码将字符串转换为**DateTime**格式：  
  
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
  
## <a name="writing-strings-as-types"></a>将字符串作为类型写入  
 下面的示例读取**Int32**并将其转换为字符串。  
  
 给定以下 XML 输入：  
  
 **输入**  
  
```xml  
<TestInt32>-2147483648</TestInt32>  
```  
  
 下面的代码将**Int32**到**字符串**:  
  
```vb  
Dim vInt32 As Int32 = -2147483648  
writer.WriteElementString("TestInt32", XmlConvert.ToString(vInt32))  
```  
  
```csharp  
Int32 vInt32=-2147483648;  
writer.WriteElementString("TestInt32",XmlConvert.ToString(vInt32));  
```  
  
## <a name="see-also"></a>另请参阅  
 [将字符串转换为.NET Framework 数据类型](../../../../docs/standard/data/xml/converting-strings-to-dotnet-data-types.md)  
 [将.NET Framework 类型转换为字符串](../../../../docs/standard/data/xml/converting-dotnet-types-to-strings.md)
