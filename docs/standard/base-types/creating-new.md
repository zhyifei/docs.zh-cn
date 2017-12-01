---
title: "在.NET 中创建新的字符串"
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
helpviewer_keywords:
- CopyTo method
- Join method
- Format method
- Concat method
- strings [.NET Framework], creating
- Insert method
ms.assetid: 06fdf123-2fac-4459-8904-eb48ab908a30
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: d000cd88fc9ee9fd48ef25e9bb4982688564a2a0
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="creating-new-strings-in-net"></a>在.NET 中创建新的字符串
[!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)]允许字符串要创建使用简单赋值，并且还重载以支持使用大量不同的参数的字符串创建的类构造函数。 [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)]还提供了几种方法中的<xref:System.String?displayProperty=nameWithType>创建新的字符串的类的对象，或通过组合多个字符串，字符串的数组对象。  
  
## <a name="creating-strings-using-assignment"></a>通过赋值创建字符串  
 创建一个新的最简单办法<xref:System.String>对象只是将分配一个字符串赋给<xref:System.String>对象。  
  
## <a name="creating-strings-using-a-class-constructor"></a>使用类构造函数创建字符串  
 你可以使用的重载<xref:System.String>类构造函数来创建从字符数组的字符串。 还可以通过将特定字符重复指定次数来创建新字符串。  
  
## <a name="methods-that-return-strings"></a>返回字符串的方法  
 下表列出了返回新字符串对象的几个有用方法。  
  
|方法名称|使用|  
|-----------------|---------|  
|<xref:System.String.Format%2A?displayProperty=nameWithType>|从一组输入对象生成格式化的字符串。|  
|<xref:System.String.Concat%2A?displayProperty=nameWithType>|从两个或更多个字符串生成字符串。|  
|<xref:System.String.Join%2A?displayProperty=nameWithType>|通过合并字符串数组生成新字符串。|  
|<xref:System.String.Insert%2A?displayProperty=nameWithType>|通过将一个字符串插入现有字符串的指定索引处生成新字符串。|  
|<xref:System.String.CopyTo%2A?displayProperty=nameWithType>|将一个字符串中的指定字符复制到一个字符数组中的指定位置。|  
  
### <a name="format"></a>格式  
 你可以使用**String.Format**方法来创建格式化的字符串并将连接字符串表示多个对象。 此方法自动将传递给它的任何对象转换为字符串。 例如，如果你的应用程序必须显示**Int32**值和**DateTime**值对用户来说，你可以轻松地构建一个字符串，若要使用这些值表示**格式**方法。 有关此方法使用的格式化约定的信息，请参阅有关[复合格式化](../../../docs/standard/base-types/composite-formatting.md)的部分。  
  
 下面的示例使用**格式**方法来创建使用一个整数变量的字符串。  
  
 [!code-csharp[Strings.Creating#1](../../../samples/snippets/csharp/VS_Snippets_CLR/Strings.Creating/cs/Example.cs#1)]
 [!code-vb[Strings.Creating#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Strings.Creating/vb/Example.vb#1)]  
  
 在此示例中，<xref:System.DateTime.Now%2A?displayProperty=nameWithType>以指定与当前线程关联的区域性的方式显示的当前日期和时间。  
  
### <a name="concat"></a>Concat  
 **String.Concat**方法可以用于轻松地从两个或多个现有对象创建新的字符串对象。 它提供了一种与语言无关的方法来连接字符串。 此方法接受任何派生自的类**System.Object**。 下面的示例使用两个现有字符串对象和一个分隔符创建一个字符串。  
  
 [!code-csharp[Strings.Creating#2](../../../samples/snippets/csharp/VS_Snippets_CLR/Strings.Creating/cs/Example.cs#2)]
 [!code-vb[Strings.Creating#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Strings.Creating/vb/Example.vb#2)]  
  
### <a name="join"></a>联接  
 **String.Join**方法创建新的字符串数组中的字符串和分隔符字符串。 如果想要将多个字符串连接在一起，构成一个可能由逗号分隔的列表，则此方法非常有用。  
  
 下面的示例使用空格来连接字符串数组。  
  
 [!code-csharp[Strings.Creating#3](../../../samples/snippets/csharp/VS_Snippets_CLR/Strings.Creating/cs/Example.cs#3)]
 [!code-vb[Strings.Creating#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Strings.Creating/vb/Example.vb#3)]  
  
### <a name="insert"></a>Insert  
 **String.Insert**方法通过将一个字符串插入到另一个字符串中的指定位置来创建一个新字符串。 此方法使用从零开始的索引。 下面的示例将一个字符串插入 `MyString` 的第五个索引位置，并用此值创建新字符串。  
  
 [!code-csharp[Strings.Creating#4](../../../samples/snippets/csharp/VS_Snippets_CLR/Strings.Creating/cs/Example.cs#4)]
 [!code-vb[Strings.Creating#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Strings.Creating/vb/Example.vb#4)]  
  
### <a name="copyto"></a>CopyTo  
 **String.CopyTo**方法将字符串的一部分复制到字符的数组。 可以同时指定字符串的开始索引和要复制的字符数。 此方法采用源索引、字符数组、目标索引和要复制的字符数。 所有索引都从零开始。  
  
 下面的示例使用**CopyTo**方法将单词"Hello"从字符串对象的字符复制到的字符数组的第一个索引位置。  
  
 [!code-csharp[Strings.Creating#5](../../../samples/snippets/csharp/VS_Snippets_CLR/Strings.Creating/cs/Example.cs#5)]
 [!code-vb[Strings.Creating#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Strings.Creating/vb/Example.vb#5)]  
  
## <a name="see-also"></a>另请参阅  
 [基本字符串操作](../../../docs/standard/base-types/basic-string-operations.md)  
 [复合格式设置](../../../docs/standard/base-types/composite-formatting.md)
