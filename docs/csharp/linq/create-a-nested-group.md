---
title: 创建嵌套组（C# 中的 LINQ）
description: 了解如何在 C# 中的 LINQ 查询表达式中创建嵌套组。
ms.date: 12/1/2016
ms.assetid: e9f00708-362e-4d13-98c5-d77549347ba0
ms.openlocfilehash: c973048d0859f61596c62c294131b8c00d0039f8
ms.sourcegitcommit: 4c158beee818c408d45a9609bfc06f209a523e22
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/03/2018
ms.locfileid: "37404744"
---
# <a name="create-a-nested-group"></a>创建嵌套组

以下示例演示如何在 LINQ 查询表达式中创建嵌套组。 首先根据学生年级创建每个组，然后根据每个人的姓名进一步细分为小组。

## <a name="example"></a>示例

> [!NOTE]
> 此示例包含对[查询对象集合](query-a-collection-of-objects.md)内示例代码中所定义对象的引用。

[!code-csharp[csProgGuideLINQ#24](~/samples/snippets/csharp/concepts/linq/how-to-create-a-nested-group_1.cs)]

请注意，需要使用 3 个嵌套的 `foreach` 循环来循环访问嵌套组的内部元素。

## <a name="see-also"></a>请参阅

[语言集成查询 (LINQ)](index.md)
