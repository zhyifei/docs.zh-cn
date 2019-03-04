---
title: 如何：使用字典存储事件实例 - C# 编程指南
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- events [C#], storing instances in a Dictionary
ms.assetid: 9512c64d-5aaf-40cd-b941-ca2a592f0064
ms.openlocfilehash: f3b8e313bd0b1bd3973102caebb9bbc9da620ae6
ms.sourcegitcommit: 41c0637e894fbcd0713d46d6ef1866f08dc321a2
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/01/2019
ms.locfileid: "57203027"
---
# <a name="how-to-use-a-dictionary-to-store-event-instances-c-programming-guide"></a>如何：使用字典存储事件实例（C# 编程指南）
`accessor-declarations` 的一个用途是公开多个事件，无需为每个事件分配一个字段，而是改用词典存储事件实例。 仅当拥有多个事件，但预计不会实现大多数事件时有用。  
  
## <a name="example"></a>示例  
 [!code-csharp[csProgGuideEvents#9](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideEvents/CS/Events.cs#9)]  
  
## <a name="see-also"></a>请参阅

- [C# 编程指南](../../../csharp/programming-guide/index.md)
- [事件](../../../csharp/programming-guide/events/index.md)
- [委托](../../../csharp/programming-guide/delegates/index.md)
