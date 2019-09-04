---
title: 如何：执行多态查询
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 2f05da1e-845b-4f14-83e4-c6353a850553
ms.openlocfilehash: 49e0a6b44af0729959fabf6278cc6d8ecf37a16b
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/04/2019
ms.locfileid: "70251511"
---
# <a name="how-to-execute-a-polymorphic-query"></a>如何：执行多态查询

本主题说明如何使用[OFTYPE](./language-reference/oftype-entity-sql.md)运算符执行[!INCLUDE[esql](../../../../../includes/esql-md.md)]多态查询。

### <a name="to-run-the-code-in-this-example"></a>运行本示例中的代码

1. 将[School 模型](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb896300(v=vs.100))添加到项目中，并将项目配置为使用实体框架。 有关详细信息，请参阅[如何：使用实体数据模型向导](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738677(v=vs.100))。

2. 在应用程序的代码页中，添加以下 `using` 语句（在 Visual Basic 中为 `Imports`）：

    [!code-csharp[DP EntityServices Concepts#Namespaces](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/source.cs#namespaces)]
    [!code-vb[DP EntityServices Concepts#Namespaces](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp entityservices concepts/vb/source.vb#namespaces)]

3. 按照演练中[的步骤修改概念模型，使每个层次结构一个表继承。映射继承-每个层次结构](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/cc716683(v=vs.100))一个表。

## <a name="example"></a>示例

下面的示例使用 OFTYPE 运算符从 `OnsiteCourses` 的集合中获取和显示仅包含 `Courses` 的集合。

[!code-csharp[DP EntityServices Concepts#PolymorphicQuery](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/source.cs#polymorphicquery)]
[!code-vb[DP EntityServices Concepts#PolymorphicQuery](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp entityservices concepts/vb/source.vb#polymorphicquery)]

## <a name="see-also"></a>请参阅

- [用于实体框架的 EntityClient 提供程序](entityclient-provider-for-the-entity-framework.md)
- [实体 SQL 语言](./language-reference/entity-sql-language.md)
